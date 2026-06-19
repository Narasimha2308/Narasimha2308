class Narasimha:
    def __init__(self):
        self.name = "T. Narasimha"
        self.role = [
            "Software Engineer",
            "AI Developer",
            "Data Analyst",
            "Business Analyst"
        ]

        self.education = {
            "degree": "B.Tech in Computer Science Engineering",
            "minor": "Artificial Intelligence",
            "university": "KL University",
            "cgpa": "8.88/10"
        }

        self.location = "Vijayawada, Andhra Pradesh, India"

        self.interests = [
            "Artificial Intelligence",
            "Software Development",
            "Machine Learning",
            "Data Analytics",
            "Full Stack Development",
            "Cloud Computing"
        ]

        self.skills = {
            "Languages": [
                "Python",
                "JavaScript",
                "SQL",
                "HTML",
                "CSS"
            ],

            "Frameworks & Libraries": [
                "Streamlit",
                "Pandas",
                "NumPy",
                "Matplotlib",
                "Plotly",
                "Scikit-learn",
                "Hugging Face Transformers"
            ],

            "Databases": [
                "SQLite",
                "PostgreSQL"
            ],

            "Tools": [
                "Git",
                "GitHub",
                "VS Code",
                "Power BI",
                "Excel",
                "Tableau"
            ]
        }

        self.projects = [
            "📈 OptionScope - Options Trading Analytics Platform",
            "🤖 AI Text Summarizer",
            "🌦️ Weather App",
            "💼 Job Application Tracker",
            "📊 Sales Data Analysis Dashboard"
        ]

        self.currently_learning = [
            "Machine Learning",
            "Advanced SQL",
            "Microsoft Fabric",
            "Azure",
            "Cloud Technologies",
            "Data Structures & Algorithms"
        ]

        self.certifications = [
            "Microsoft Fabric Fundamentals",
            "Power BI",
            "SQL",
            "Python",
            "Excel for Data Analytics"
        ]

        self.open_to = [
            "Software Engineering",
            "AI/ML Engineering",
            "Data Analytics",
            "Business Analytics",
            "Python Development"
        ]

    def say_hi(self):
        print("""
👋 Hello, I'm T. Narasimha!

🚀 Passionate about building AI-powered applications,
📊 transforming data into meaningful insights,
💻 and solving real-world problems through technology.

Thanks for visiting my GitHub profile!
Let's build something amazing together.
        """)


if __name__ == "__main__":
    me = Narasimha()
    me.say_hi()
