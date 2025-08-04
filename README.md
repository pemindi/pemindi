"use client"

import { useState } from "react"
import { Card, CardContent } from "@/components/ui/card"
import { Button } from "@/components/ui/button"
import { Badge } from "@/components/ui/badge"
import {
  Github,
  Mail,
  Instagram,
  MapPin,
  GraduationCap,
  Code,
  Database,
  Brain,
  Mountain,
  Music,
  Star,
  GitFork,
  Activity,
  Calendar,
  ExternalLink,
} from "lucide-react"

const skills = {
  "Programming Languages": [
    { name: "Python", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "JavaScript", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "Java", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "Kotlin", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "C/C++", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "PHP", color: "bg-gray-700 hover:bg-gray-600" },
  ],
  "Web Technologies": [
    { name: "React", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "Node.js", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "Express.js", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "HTML5", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "CSS3", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "TailwindCSS", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "Bootstrap", color: "bg-gray-700 hover:bg-gray-600" },
  ],
  Databases: [
    { name: "MongoDB", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "MySQL", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "SQL Server", color: "bg-gray-700 hover:bg-gray-600" },
  ],
  "Tools & Others": [
    { name: "Figma", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "Android", color: "bg-gray-700 hover:bg-gray-600" },
    { name: "Git", color: "bg-gray-700 hover:bg-gray-600" },
  ],
}

const currentFocus = [
  {
    icon: <Brain className="w-5 h-5" />,
    title: "AI & Machine Learning",
    description: "Interested in research and further study, especially in AI and related fields",
  },
  {
    icon: <Star className="w-5 h-5" />,
    title: "Final Year Research",
    description: "Working on applications of AI in astronomy for academic research",
  },
  {
    icon: <Activity className="w-5 h-5" />,
    title: "Data Analysis",
    description: "Developing skills in data visualization and analytical tools",
  },
  {
    icon: <Code className="w-5 h-5" />,
    title: "Open Source",
    description: "Contributing to open-source projects and learning from the community",
  },
]

const githubStats = {
  totalRepos: 42,
  totalStars: 156,
  totalForks: 23,
  contributions: 847,
  streak: 23,
}

export default function PemindiProfile() {
  const [activeTab, setActiveTab] = useState("about")

  return (
    <div className="min-h-screen bg-black">
      {/* Hero Section */}
      <div className="relative overflow-hidden">
        <div className="absolute inset-0 bg-gradient-to-b from-gray-900 to-black"></div>
        <div className="relative container mx-auto px-4 py-16">
          <div className="text-center">
            <div className="mb-6">
              <div className="w-32 h-32 mx-auto rounded-full bg-white p-1">
                <div className="w-full h-full rounded-full bg-black flex items-center justify-center border border-gray-700">
                  <span className="text-4xl font-bold text-white">P</span>
                </div>
              </div>
            </div>
            <h1 className="text-5xl font-bold text-white mb-4">
              Hi 👋, I'm <span className="text-gray-300">Pemindi</span>
            </h1>
            <div className="flex flex-wrap justify-center gap-4 text-gray-400 mb-6">
              <div className="flex items-center gap-2">
                <GraduationCap className="w-5 h-5 text-gray-300" />
                <span>3rd Year IT - Data Science Student</span>
              </div>
              <div className="flex items-center gap-2">
                <MapPin className="w-5 h-5 text-gray-300" />
                <span>SLIIT</span>
              </div>
            </div>
            <p className="text-xl text-gray-300 max-w-2xl mx-auto mb-8">
              Passionate about <span className="text-white font-medium">Data Science</span>,
              <span className="text-white font-medium"> Machine Learning</span>, and
              <span className="text-white font-medium"> AI</span>. Exploring new technologies and contributing to
              open-source projects.
            </p>

            {/* Contact Buttons */}
            <div className="flex flex-wrap justify-center gap-4">
              <Button className="bg-white text-black hover:bg-gray-200">
                <Mail className="w-4 h-4 mr-2" />
                Email Me
              </Button>
              <Button
                variant="outline"
                className="border-gray-400 text-gray-300 hover:bg-gray-800 hover:text-white bg-transparent"
              >
                <Instagram className="w-4 h-4 mr-2" />
                Instagram
              </Button>
              <Button
                variant="outline"
                className="border-gray-400 text-gray-300 hover:bg-gray-800 hover:text-white bg-transparent"
              >
                <Github className="w-4 h-4 mr-2" />
                GitHub
              </Button>
            </div>
          </div>
        </div>
      </div>

      {/* Navigation Tabs */}
      <div className="container mx-auto px-4">
        <div className="flex justify-center mb-8">
          <div className="bg-gray-900 border border-gray-700 rounded-lg p-1">
            {["about", "skills", "stats", "focus"].map((tab) => (
              <Button
                key={tab}
                variant={activeTab === tab ? "default" : "ghost"}
                className={`capitalize ${
                  activeTab === tab
                    ? "bg-white text-black hover:bg-gray-200"
                    : "text-gray-400 hover:text-white hover:bg-gray-800"
                }`}
                onClick={() => setActiveTab(tab)}
              >
                {tab}
              </Button>
            ))}
          </div>
        </div>

        {/* Content Sections */}
        <div className="max-w-6xl mx-auto pb-16">
          {activeTab === "about" && (
            <Card className="bg-gray-900 border-gray-700">
              <CardContent className="p-8">
                <h2 className="text-3xl font-bold text-white mb-6 flex items-center gap-3">
                  <span className="text-gray-300">⚡</span>
                  About Me
                </h2>
                <div className="grid md:grid-cols-2 gap-8">
                  <div>
                    <h3 className="text-xl font-semibold text-gray-200 mb-4">What I Do</h3>
                    <p className="text-gray-400 leading-relaxed mb-6">
                      I'm a Data Science student with a focus on AI and Machine Learning. Currently working on my final
                      year research project that explores AI applications in astronomy. I enjoy learning about new
                      technologies and methodologies in the field.
                    </p>
                    <p className="text-gray-400 leading-relaxed">
                      I also contribute to open-source projects when possible and am always looking to expand my
                      knowledge through practical applications and collaborative work.
                    </p>
                  </div>
                  <div>
                    <h3 className="text-xl font-semibold text-gray-200 mb-4">Interests</h3>
                    <div className="space-y-4">
                      <div className="flex items-center gap-3 text-gray-400">
                        <Mountain className="w-5 h-5 text-gray-300" />
                        <span>Hiking and outdoor activities</span>
                      </div>
                      <div className="flex items-center gap-3 text-gray-400">
                        <Music className="w-5 h-5 text-gray-300" />
                        <span>Music and audio technology</span>
                      </div>
                      <div className="flex items-center gap-3 text-gray-400">
                        <Code className="w-5 h-5 text-gray-300" />
                        <span>Software development and programming</span>
                      </div>
                    </div>
                  </div>
                </div>
              </CardContent>
            </Card>
          )}

          {activeTab === "skills" && (
            <div className="space-y-6">
              {Object.entries(skills).map(([category, skillList]) => (
                <Card key={category} className="bg-gray-900 border-gray-700">
                  <CardContent className="p-6">
                    <h3 className="text-xl font-semibold text-white mb-4 flex items-center gap-2">
                      <Database className="w-5 h-5 text-gray-300" />
                      {category}
                    </h3>
                    <div className="flex flex-wrap gap-3">
                      {skillList.map((skill) => (
                        <Badge
                          key={skill.name}
                          className={`${skill.color} text-white transition-colors cursor-pointer border border-gray-600`}
                        >
                          {skill.name}
                        </Badge>
                      ))}
                    </div>
                  </CardContent>
                </Card>
              ))}
            </div>
          )}

          {activeTab === "stats" && (
            <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-6">
              <Card className="bg-gray-900 border-gray-700">
                <CardContent className="p-6 text-center">
                  <Github className="w-8 h-8 text-gray-300 mx-auto mb-3" />
                  <div className="text-3xl font-bold text-white mb-1">{githubStats.totalRepos}</div>
                  <div className="text-gray-400">Total Repositories</div>
                </CardContent>
              </Card>

              <Card className="bg-gray-900 border-gray-700">
                <CardContent className="p-6 text-center">
                  <Star className="w-8 h-8 text-gray-300 mx-auto mb-3" />
                  <div className="text-3xl font-bold text-white mb-1">{githubStats.totalStars}</div>
                  <div className="text-gray-400">Total Stars</div>
                </CardContent>
              </Card>

              <Card className="bg-gray-900 border-gray-700">
                <CardContent className="p-6 text-center">
                  <GitFork className="w-8 h-8 text-gray-300 mx-auto mb-3" />
                  <div className="text-3xl font-bold text-white mb-1">{githubStats.totalForks}</div>
                  <div className="text-gray-400">Total Forks</div>
                </CardContent>
              </Card>

              <Card className="bg-gray-900 border-gray-700">
                <CardContent className="p-6 text-center">
                  <Activity className="w-8 h-8 text-gray-300 mx-auto mb-3" />
                  <div className="text-3xl font-bold text-white mb-1">{githubStats.contributions}</div>
                  <div className="text-gray-400">Contributions</div>
                </CardContent>
              </Card>

              <Card className="bg-gray-900 border-gray-700">
                <CardContent className="p-6 text-center">
                  <Calendar className="w-8 h-8 text-gray-300 mx-auto mb-3" />
                  <div className="text-3xl font-bold text-white mb-1">{githubStats.streak}</div>
                  <div className="text-gray-400">Day Streak</div>
                </CardContent>
              </Card>

              <Card className="bg-gray-900 border-gray-700">
                <CardContent className="p-6 text-center">
                  <ExternalLink className="w-8 h-8 text-gray-300 mx-auto mb-3" />
                  <div className="text-3xl font-bold text-white mb-1">Active</div>
                  <div className="text-gray-400">Status</div>
                </CardContent>
              </Card>
            </div>
          )}

          {activeTab === "focus" && (
            <div className="grid md:grid-cols-2 gap-6">
              {currentFocus.map((item, index) => (
                <Card key={index} className="bg-gray-900 border-gray-700 hover:border-gray-600 transition-colors">
                  <CardContent className="p-6">
                    <div className="flex items-start gap-4">
                      <div className="p-3 bg-gray-800 rounded-lg text-gray-300 border border-gray-700">{item.icon}</div>
                      <div>
                        <h3 className="text-xl font-semibold text-white mb-2">{item.title}</h3>
                        <p className="text-gray-400 leading-relaxed">{item.description}</p>
                      </div>
                    </div>
                  </CardContent>
                </Card>
              ))}
            </div>
          )}
        </div>
      </div>

      {/* Footer */}
      <div className="bg-gray-900 border-t border-gray-700">
        <div className="container mx-auto px-4 py-8 text-center">
          <p className="text-gray-400 mb-4">Thanks for visiting! Feel free to connect and collaborate.</p>
          <div className="flex justify-center gap-4">
            <Button size="sm" className="bg-white text-black hover:bg-gray-200">
              <Mail className="w-4 h-4 mr-2" />
              pemii2002codeprac@gmail.com
            </Button>
            <Button
              size="sm"
              variant="outline"
              className="border-gray-400 text-gray-300 hover:bg-gray-800 hover:text-white bg-transparent"
            >
              <Instagram className="w-4 h-4 mr-2" />
              @pemindi_w_02
            </Button>
          </div>
        </div>
      </div>
    </div>
  )
}
