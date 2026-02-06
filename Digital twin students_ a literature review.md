# Digital twin students: a literature review

**Introduction**  
In 2026, OpenAI and AI Leap Foundation released a **ChatGPT tool** for high-school students in Estonia, with the specific design aim of supporting learning. The **conversation texts and numerical graders** for analysing the texts provide us with an unique dataset for potentially **creating digital twin archetypes** **(roughly 3-15)** **of Estonian high school students**. 

The first aim of creating such digital twins is **to correlate such archetypes and their behavior in the tool with the students' reading ability**, as the strongest available PII-free metric related to general academic success.

**Project specs**

1. Training  
   1. Retrieve **student** **numerical graders**, with each student as a data point, each grader as a feature/dimension  
   2. Perform **unsupervised clustering** on the students, based on the graders  
      1. *Unsupervised clustering: what could be the **precise method(s)** here?*  
   3. Retrieve **conversation texts**, and seperate them to the same clusters as the grader clusters.  
   4. Feed the conversation texts of each **conversation text cluster** to a respective **digital twin student (LLM)**  
      1. Option 1: create a **database** for each **general LLM twin** to utilize at production  
         1. *What could be the **precise method(s)** here?*  
            1. RAG  
            2. Vectorspace  
      2. Option 2: perform **post-training** on an LLMs for each twin  
         1. *What could be the **precise method(s)** here?*  
2. Validation  
   1. Retrieve **student** **conversation texts**, and seperate them to the same clusters as the grader clusters. (Same as training step 3).  
   2. Using the **students' side of conversation texts**, estimate predicted **reading ability** with **various metrics**  
      1. *What could be the **precise method(s)** here?*  
         1. Gemini provided some options  
   3. Perform **unsupervised clustering** of the students, based on the **reading ability metrics**  
      1. *What could be the **precise method(s)** here?*  
   4. Create **twin conversation texts** with each **digital twin student**, with a cluster for each twin.  
      1. *What could be the **precise method(s)** here?*  
   5. Repeat validation step B and C with **twin conversation texts**  
   6. **Compare the similarity** of the clustering of the students and the twins  
      1. *What could be the **precise method(s)** here?*

   
**Meta articles**  
[Digital Twins for Education: A Literature Review | Anais do Simpósio Brasileiro de Informática na Educação (SBIE)](https://sol.sbc.org.br/index.php/sbie/article/view/31280)

**Body**

| Theme | Title | Time | Abstract | Motivation, problem addressed, core question | Methodology and outcome | Key elements | Your critique | Relevant to our project how? | Author of review |
| :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- | :---- |
| Digital Twins of Students | [AI-Based Digital Twins of Students: A New Paradigm for Competency-Oriented Learning Transformation](https://scholar.google.com/citations?view_op=view_citation&hl=en&user=CBNyXEsAAAAJ&cstart=20&pagesize=80&citation_for_view=CBNyXEsAAAAJ:yB1At4FlUx8C) | September 2025 | Universities face growing pressure to deliver personalized learning that prepares students with adaptable, future-ready competencies. Traditional static curricula are often unable to meet these demands. This paper introduces a novel framework based on AI-enhanced digital twins of students (DTS) as dynamic virtual representations integrating academic performance, competency attainment, learning preferences, career objectives, and engagement patterns. The DTS framework employs artificial intelligence algorithms, semantic ontologies spanning educational and career domains, and real-time feedback mechanisms for personalized learning pathway orchestration. To demonstrate the framework’s potential, a simulation study was conducted using synthetic student data. Results compared DTS-guided adaptive pathways with traditional static approaches and showed improvements in competency attainment, engagement, learning efficiency, and reduced dropout risk. | DTS-guided adaptive pathways vs. traditional static approaches | **Simulation study** showed **improvements in competency attainment, engagement, learning efficiency, and reduced dropout risk,** compared against traditional approaches. | **In the study:** Digital twins of students (DTS), synthetic student data, simulation study.  **Mentioned:** Learning managements systems (LMSs), student information systems (SISs), education-as-a-service (EaaS).  | **Applicability to real life 1\)**  The presented framework has **a lot of different data for equally many different real-time predictions**. Begs the question: **how accurate is this all really?** (as only a sim. study was conducted) *(Note: at p. 3).* **2\)**  The study presents an unified framework that **requires a lot of PII data** alongside other types of data that are hard to quantify and efficiently utilize. The **model can suggest a lot of things** from these data features, however **only at a consulting level.** (as if it all were simply pre-prompted/in-memory) *(Note: have not looked at meth. yet, p. 5\)* **Lack of focus 1\)** The presented framework in the study is designed as an unified system: nevertheless, especially with the lack of proof of it actually working with real data, it is attempting to derive *a lot* of predictions from  | **Relevant: 1\)**  The framework built in the paper features a wide array of data – albeit overtly mathematical/rudimentary in modelling that, it offers **ideas on how to feed data into a digital twin** system and **make it adaptive** to the student. **2\) Actionable output from student data** and **action-based intervention** from the model is quite an useful mechanism. **Irrelevant:** The framework (theoretically)  ulitizes a lot of **personal student data**, from student information systems – our project constraints do not *typically* allow for this. | Hendrik |
| Digital Twins for Personalized Learning | [Proposed Student Digital Twin Data Model and System Architecture for Personalized Learning](https://ieeexplore.ieee.org/document/11115606)  | May 2025 | Education systems worldwide are tending to replace the standardized learning techniques with a more customized, student-tailored approach, in order to allow students advance according to their own capabilities and circumstances. Personalization of learning can be improved by **integrating the concepts of human digital twin (DT)**, which is based on real-time data, together with artificial intelligence (AI). This integration enables the use of real-time data about students, which improves the understanding of their needs. Therefore, a more effective personalized learning experience that tends to be more adaptive could be achieved. This research proposes an architecture for a system that captures real-time data from students using data capturing tools and IoT devices, analyzes these data, and give real-time feedback to guide students during their learning process. The main objective is to decrease the percentage of student's failure rate and highlight students with excelling performance. In this research, the set of attributes that properly defines a digital real-time copy of a student are defined, the tools that can capture these attributes are determined, a model of a digital student in a learning environment is developed, and the architecture of the overall system, and its potential uses are discussed. Finally, an experiment is conducted to test the proposed student digital twin model, and system architecture and results are highlighted. |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |
|  |  |  |  |  |  |  |  |  |  |

