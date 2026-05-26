# Failure Patterns

## Stops At Topic Selection

Problem: The agent lists candidates and asks the user to choose.

Fix: Candidate topics are records, not pause points. Choose Top 1 automatically and continue.

## Turns Into Knowledge Cards

Problem: The comic becomes PPT, cards, posters, or abstract concept slides.

Fix: Use concrete characters, scenes, objects, and actions. Every panel should show something happening in a real place.

## Uses Script Placeholder Images

Problem: Local drawing scripts create geometric people or abstract scenes.

Fix: Do not use placeholder images as final images. Use image generation tools for base images or output image worker prompts.

## White Caption Boxes Or Black Bars

Problem: Subtitles appear as white blocks, black bars, or large translucent panels.

Fix: Use no-background outlined text with subtle shadow.

## Zhihu Becomes An Essay

Problem: The article starts with definitions and explanatory headings.

Fix: Tell the complete fable first, then add one "作者的话".

## Pretends Images Exist

Problem: The output references image paths even though no images were generated.

Fix: If images were not generated, output an insertion plan and state that images are pending.

## Leaks Private Context

Problem: The output references local paths, private documents, private memory, or account environment.

Fix: Treat the user as an external user and rely only on the provided public skill.

