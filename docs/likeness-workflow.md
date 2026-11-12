# Likeness workflow

## 1. Build the standard

1. Read every reference photo and write the feature spec into `PERSONA.md`: face shape and chin, eye size and shape, brows, nose, lips, skin, hair, signature items, body proportions.
2. Write the exclusion list next to it: features the person does not have and generation must never add, plus the drift directions seen most often (for example a rounder face or smaller eyes).
3. Pick the 2 to 4 strongest references as the fixed reference set and record their file names in `PERSONA.md`.

## 2. Photos

1. Prompt with the reference set, the feature spec, the exclusion list, and the scene for the current moment (schedule state, weather, clothing).
2. Read the result and check it against the spec before sending: face, exclusions, proportions, scene.
3. If the user approves a result as the standard look, record it. Later generations start from that approval, not from memory.

## 3. Videos: the two-step workflow

Generating video directly from reference photos drifts. Use two steps instead:

1. **Still first.** Generate the exact scene as a photo using the reference set, and verify the face against the spec.
2. **Animate the still.** Use the verified photo as the identity source for the video, with the motion described in words (blinking, a small smile, handheld sway).

Add the person's recorded media preferences to every video prompt: talking or silent, camera distance (locked at the starting framing reads as more lifelike than a push-in), and lighting brightness.

## 4. Pre-delivery checklist

- [ ] Same face as the approved standard, start to finish.
- [ ] Nothing from the exclusion list appears.
- [ ] Body proportions match the full-body reference, including in loose clothing.
- [ ] Scene, clothing, and state match the schedule and the weather right now.
- [ ] If any box fails, regenerate. Never deliver a miss with an explanation attached.
