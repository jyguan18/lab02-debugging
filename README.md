# lab02-debugging

I worked with Rebecca Waterson and Logan Dooley on this lab.
[Shadertoy Link](https://www.shadertoy.com/view/WfffWl)

Bug #1: Right off the bat, the program would not load because of a syntax error. Luckily, shadertoy told us where and what the error was. There is no "vec", so I just changed it to "vec2".

Bug #2: The angle looked wrong for what we were viewing - the balls were very large. We realized uv2 was never actually used after being declared so we put it in the raycast() call and the view looked a lot better.

Bug #3: The output looked very stretched out, which kind of implied a raycast error. H was dividing iResolution.x with iResolution.x but it should have been dividing by iResolution.y. Dividing it by itself will always result in 1.0, which is not the correct aspect ratio for when the screen isn't a square.

Bug #4: The background/floor looked like it got cut off. So instead of the ray march stopping at 64, we increased it to 128 and it looked a lot better.

Bug #5: Now clearly there is a reflection error. We checked the normals first and it looked fine. We realized reflect() should not take in eye but instead dir, and that fixed the reflection.

# Setup 

Create a [Shadertoy account](https://www.shadertoy.com/). Either fork this shadertoy, or create a new shadertoy and copy the code from the [Debugging Puzzle](https://www.shadertoy.com/view/flGfRc).

Let's practice debugging! We have a broken shader. It should produce output that looks like this:
[Unbelievably beautiful shader](https://user-images.githubusercontent.com/1758825/200729570-8e10a37a-345d-4aff-8eff-6baf54a32a40.webm)

It don't do that. Correct THREE of the FIVE bugs that are messing up the output. You are STRONGLY ENCOURAGED to work with a partner and pair program to force you to talk about your debugging thought process out loud.

Extra credit if you can find all FIVE bugs.

# Submission
- Create a pull request to this repository
- In the README, include the names of both your team members
- In the README, create a link to your shader toy solution with the bugs corrected
- In the README, describe each bug you found and include a sentence about HOW you found it.
- Make sure all three of your shadertoys are set to UNLISTED or PUBLIC (so we can see them!)
