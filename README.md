# interactive-story-time
An interactive story-telling "console" designed to make programming your own stories easy using a YAML-based parser. Uses the WPF framework to render buttons/text in a pleasing way on Windows 10.

### Example Story Script
- Name the file story.yaml and place it in binary path
- Copy and paste the following script to get started:

```
---
pages:
  - pageNo: 1
    textOpen: "You read page 1's opening text."
    storyButtons:
      - num: 0
        go: 2
        text: "Turn to page 2"
      - num: 1
        go: 3
        text: "Skip to page 3"
  - pageNo: 2
    textOpen: >-
      You reach page 2.
      Once you've fully read it, you must decide what to do next.
    textClose: "You close page 2."
    storyButtons:
      - num: 0
        go: 1
        text: |-
          Go to
          Page 1
      - num: 3
        go: 3
        text: |-
          Go to
          Page 3
  - pageNo: 3
    textOpen: "This is the first time you've read page 3!"
    textReturn: "You've read page 3 before..."
    storyButtons:
      - num: 0
        go: 1
        text: "Restart Story"
      - num: 1
        go: 4
        text: "End Story"
  - pageNo: 4
    textOpen: "The story is over!"
    storyButtons: []
```

### Credits
- Walter Macfarland (Epitaph64) for this project
- YamlDotNet (Deserialize YAML format for story loading):
  - https://github.com/aaubry/YamlDotNet

### Ideas for Future Improvement
- Proper error handling, particularly passing YAML parser errors to game console instead of crashing.
- Story load function / story browser
- Ability to restart a story (perhaps via hotkey which prompts user)
- Story format (using YAMLDotNet to provide YAML deserialization):
  - Add metadata (author name, story title, etc.)
  - Change font family, button colors, "console" printout background/foreground colors.
  - For much later, perhaps even integrating the ability to allow more advanced authors to use HTML/CSS to style the way the text generated by pages/buttons appears.

