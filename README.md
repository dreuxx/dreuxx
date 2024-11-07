import json
import base64
from typing import List, Dict

class GitHubProfileGenerator:
    def __init__(self):
        self.frames = [
            self._create_frame_1(),
            self._create_frame_2(),
            self._create_frame_3(),
            self._create_frame_4()
        ]
        
    def _create_frame_1(self) -> str:
        return '''
```ascii
╔══════════════════════════════════════════╗
║     👨‍💻 Giovanny Rodríguez             ║
║     🎓 Computer Science & Mathematics     ║
╚══════════════════════════════════════════╝

< Scrolling through my skills... >
   \\
    \\
      __
     /  \\
    /    \\
   |  ^_^ |
   |      |
   |      |
    \\____/
```
'''

    def _create_frame_2(self) -> str:
        return '''
```ascii
╔══════════════════════════════════════════╗
║ 🔧 Technical Skills:                      ║
║ • Python, C++, JavaScript, MATLAB        ║
║ • Data Science & Machine Learning        ║
║ • Information Security                   ║
╚══════════════════════════════════════════╝

< Loading more... >
   \\
    \\
     (•◡•)
      |__|
      |  |
      |__|
```
'''

    def _create_frame_3(self) -> str:
        return '''
```ascii
╔══════════════════════════════════════════╗
║ 🚀 Projects:                             ║
║ • Explorer Transportation Data Science   ║
║ • Grammar Checker Chrome Extension       ║
║ • Rise of Kingdoms Bot                   ║
╚══════════════════════════════════════════╝

< Almost there... >
   \\
    \\
    (づ｡◕‿‿◕｡)づ
```
'''

    def _create_frame_4(self) -> str:
        return '''
```ascii
╔══════════════════════════════════════════╗
║ 📫 Contact:                              ║
║ • Email: dreuxxr@gmail.com              ║
║ • Location: Brooklyn, NY                 ║
║ • Languages: Spanish, English            ║
╚══════════════════════════════════════════╝

< Welcome to my profile! >
   \\
    \\
   (∩｀-´)⊃━☆ﾟ.*･｡ﾟ
```
'''

    def generate_readme(self) -> str:
        """Generate the complete README.md content with animation."""
        readme_content = """
<div align="center">

# ¡Hola! 👋 I'm Giovanny Rodríguez

![Typing SVG](https://readme-typing-svg.herokuapp.com?font=Fira+Code&pause=1000&color=2196F3&center=true&vCenter=true&width=435&lines=Computer+Science+Student;Mathematics+Enthusiast;Machine+Learning+Developer;Always+Learning)

<div align="center">
    <img src="profile-animation.gif" alt="Profile Animation" />
</div>

## 🎯 Current Focus

- 🎓 Studying Computer Science & Mathematics at CUNY College of Staten Island
- 💡 Developing skills in Machine Learning and Data Science
- 🔒 Learning about Cybersecurity
- 🌱 Improving my English proficiency

## 🛠️ Technologies & Tools

![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=Python&logoColor=white)
![C++](https://img.shields.io/badge/-C++-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)
![JavaScript](https://img.shields.io/badge/-JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![MATLAB](https://img.shields.io/badge/-MATLAB-0076A8?style=flat-square&logo=mathworks&logoColor=white)

## 📊 GitHub Stats

<img src="https://github-readme-stats.vercel.app/api?username=YourGitHubUsername&show_icons=true&theme=tokyonight" alt="GitHub Stats" />

## 🌟 Featured Projects

### [Explorer Transportation Data Science Project](https://nebigdatahub.org/nsdc/tdsp/)
Advanced transportation data analysis using machine learning techniques

### [Grammar Checker Chrome Extension](https://chromewebstore.google.com/detail/grammar-checker-multi-lan/dcgfjejbncgnpgiciceafjegfiiiblpi)
Multi-language grammar checking extension with OpenAI integration

### Rise of Kingdoms Bot
Automated resource collection bot with multi-account management

## 📫 Connect with Me

[![LinkedIn](https://img.shields.io/badge/-LinkedIn-0077B5?style=flat-square&logo=LinkedIn&logoColor=white)](https://www.linkedin.com/in/giovanny-rodr%C3%ADguez-)
[![Email](https://img.shields.io/badge/-Email-D14836?style=flat-square&logo=Gmail&logoColor=white)](mailto:dreuxxr@gmail.com)

</div>
"""
        return readme_content

    def save_animation_frames(self, output_dir: str = "./") -> None:
        """Save each frame as a separate file."""
        for i, frame in enumerate(self.frames, 1):
            with open(f"{output_dir}frame_{i}.txt", "w", encoding="utf-8") as f:
                f.write(frame)

def main():
    # Create the generator
    generator = GitHubProfileGenerator()
    
    # Generate and save the README.md
    readme_content = generator.generate_readme()
    with open("README.md", "w", encoding="utf-8") as f:
        f.write(readme_content)
    
    # Save animation frames
    generator.save_animation_frames()
    
    print("Generated README.md and animation frames successfully!")
    print("Note: You'll need to convert the frames to GIF using a tool like ImageMagick")
    print("Example ImageMagick command:")
    print("convert -delay 100 -loop 0 frame_*.txt profile-animation.gif")

if __name__ == "__main__":
    main()

