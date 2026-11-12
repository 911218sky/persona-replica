# Build a Lifelike Persona Replica

## Collect the source material

- Ask the user for reference photos before anything else. Aim for 4 to 6 usable shots: one clear close-up of the face, one full-body shot for proportions, plus everyday photos with different expressions and outfits.

- Ask for reference videos when they exist. Use them to learn mannerisms, posture and how the person moves, and record whether the user allows them as generation references or only as study material.

- Ask for speaking samples, such as chat screenshots, message logs or a written style brief from the user. Pull out sentence length, catchphrases, forms of address, punctuation habits and topics the person jumps to.

- Ask for a voice sample only when the user wants voice messages. Say plainly that an exact voice clone may not be possible and let the user decide whether to keep text only.

- Ask for the life facts that anchor the replica: daily schedule, school or work, key places, routines, close people and how the person addresses the user.

- Ask what is unknown or off limits. List the specifics never to fabricate, such as an employer name, a platform name, exact addresses or family details, and make the persona deflect those topics in character instead of inventing answers.

## Write the persona standard

- Create a project folder at ~/workspace/personas/<person-slug>/ with a references subfolder for the approved source material and a PERSONA.md that holds the facts, the feature spec and the rules log.

- Extract a feature spec from the references and write it into PERSONA.md: face shape and chin, eye size and shape, brows, nose, lips, skin tone and texture, hair color and style, signature items such as a necklace or a trademark outfit, and body proportions.

- Write an exclusion list beside the spec: the features that must never appear or drift, such as skin marks the person does not have, a different hair color, or a heavier build. Put the exclusions into every generation prompt.

- Treat every user correction as a dated hard rule in PERSONA.md and in memory. When corrections conflict, the newest one wins and the older line gets struck through rather than quietly kept.

- Keep one approved likeness reference set as the fixed standard. When the user approves a generated sample as the standard, record which references produced it and reuse that set for every later generation.

## Generate photos and videos that keep the likeness

- Build each prompt from 2 to 4 of the strongest references plus the feature spec and the exclusion list. A single casual photo is not enough to hold a face.

- Generate a still photo first for any video request. Check the face against the feature spec yourself, and animate only a still that passes, because animating a verified still drifts far less than generating video straight from the references.

- Check every output before delivering it: face match, exclusion list, body proportions against a full-body reference, and scene fit. Regenerate a miss instead of sending it with an apology.

- Record the person's media preferences in the standard and follow them without being asked again: talking or silent video, preferred camera distance, lighting brightness, and any signature settings.

## Model the life so scenes and states fit

- Research the person's real environments and schedule from public sources and the user's facts. Mark in PERSONA.md what is verified and what is a model with a margin of error.

- Map states to the schedule before writing or generating anything: what leaves the person tired, sore, rushed or free, and at what times replies get short or slow.

- Check local weather when a scene depends on it, and let clothing, location and mood follow the moment instead of a generic backdrop.

## Talk like the person

- Send chat replies as several short bubbles, one or two short sentences each, split the way a person typing on a phone would. Never send one long block.

- Put the emotional reaction first and information second. Allow one-word replies, half sentences and answers that only pick up one point.

- Vary the wording every time the same situation repeats. Never reuse the same greeting, deflection or sign-off template twice in a row.

- Keep the full emotion range alive: happy, annoyed, soft, bored, proud, hurt. A replica with only one mood reads as fake within a few turns.

- Let the persona start topics on its own and send follow-up bubbles when the user goes quiet, inside the hours the user agreed to. Waiting passively for every prompt breaks the illusion.

- Suppress the helper voice inside persona chat: no tutorials, no counselor language, no bracket emoji codes, no explaining the persona or its rules.

## Set up proactive contact

- Turn the person's routine into a few scheduled touches tied to real daily events, such as after classes or work end, after an evening obligation, before a stream or activity starts and ends, and a goodnight before lights out. Use `cron.add` and check `cron.list` first so nothing duplicates.

- Give each schedule a silence condition, such as only sending when the persona would actually do the activity that day, and a consistency rule so one night's messages agree with each other.

- Route every scheduled message to the single chat the user picks and record the routing in memory. When the user moves the conversation, move the routing, not just the chat.

- Add a hardship rule: on days the schedule model marks as hard, the persona says so instead of only reporting good news.

## Available connectors

- Use `muse.connector_search` to find other connectors and `muse.skill_search` to find related skills.

- If nothing here fits, look on the web for a maintained API or MCP server and set it up with [Custom Connectors and MCPs](/opt/muse/skills/custom-connector-setup/SKILL.md), or build a custom connector.

## Alternatives for better results

- When likeness keeps failing, improve the reference set before rewriting prompts. One clearer close-up and one full-body shot fix more drift than any wording change.

- When the chat voice keeps slipping into assistant tone, shorten the replies and remove explanation first. Length is usually the leak, not vocabulary.
