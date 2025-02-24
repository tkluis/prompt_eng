![GenI-banner](https://github.com/genilab-fau/genilab-fau.github.io/blob/8d6ab41403b853a273983e4c06a7e52229f43df5/images/genilab-banner.png?raw=true)

# Automated Prompt Engineering in SDLC: Advanced Requirement Analysis for Machine Learning Models

The project investigates the use of automated prompt engineering within the Software Development Life Cycle to refine requirement analysis, aiming to optimize and innovate the development of sophisticated machine learning by leveraging advanced AI techniques.

* Authors: [Tim Kluis](https://www.linkedin.com/in/timkluis/)
* Academic Supervisor: [Dr. Fernando Koch](http://www.fernandokoch.me)


# Research Question 
How can automated prompt engineering improve the requirement analysis within the SDLC to enhance the accuracy and effectiveness of machine learning models?

## Arguments

#### Background

Automated prompt engineering can streamline the process of gathering and refining requirements by generating precise and tailored questions, helping stakeholders better articulate their needs and objectives. A challenge of accurately interpreting stakeholder inputs is ensuring that the AI model understands and correctly interprets stakeholder inputs, as ambiguities in natural language can lead to inaccurate requirement definitions. AI-driven prompt engineering could potentially analze historical data and trends to predict potential constraints and opportunities in the development phase, offering insights that might not be immediately evident through traditional analysis methods. By automating and enhancing the requirement analysis process through prompt engineering, AI  has the potential to significantly reduce development time and the likelihood of errors, resulting in more reliable and effective end products.

#### Prompt-Engineering Approaches Reviewed

The field of natural language processing (NLP) has witnessed significant advancements in recent years, driven in part by the development of large-scale language models. However, these models often struggle with generating coherent and informative responses to complex prompts or open-ended questions. This limitation highlights the need for effective prompt engineering techniques that can elicit desired responses from these models.

In this research, we explore two novel approaches to prompt engineering: zero-shot prompting and meta-prompting. Zero-shot prompting involves modifying temperature and context parameters to generate more accurate and relevant responses without requiring explicit training data. Our zero-shot approach allowed us to quickly explore the potential of prompt engineering without requiring extensive labeled data or computational resources. While this method may not have achieved state-of-the-art results, it provided valuable insights into the model's behavior and the feasibility of using prompt engineering techniques as a standalone solution.
    
Meanwhile, meta-promoting leverages the model's ability to generate its own prompts using a few-shot approach, which are then used as input for itself, again leveraging temperature and context parameters to tune. To implement this strategy, we experimented with adjusting the temperature parameter, which controls the probability of sampling high- versus low-probability tokens, as well as modifying the context parameters, such as the prompt's length and structure. By manipulating these variables, we aimed to find an optimal combination that would elicit more accurate and relevant responses from the model.

Our investigation into these techniques aimed to improve the language model's performance in generating informative and accurate responses. By combining insights from zero-shot prompting and meta-promoting, we sought to develop novel strategies that can adapt to diverse contexts and user queries.

In this research report, we present our findings on the effectiveness of zero-shot prompting and meta-promoting for improving language model performance. 


#### Implications

Our research has practical implications for various aspects of SDLC requirements creation, including:

* **Requirements Elicitation**: By generating prompts that effectively elicit information from stakeholders and subject matter experts, we can improve the accuracy and completeness of software requirements.
    
* **Use Case Development**: Automated prompt generation can help developers create high-quality use cases, which are critical for designing effective software systems.
    
* **Test Case Generation**: Our research can contribute to the development of test cases that effectively cover all possible scenarios, ensuring that software meets customer needs.


# Research Method

This study employed a combination of existing tools and techniques to investigate the effectiveness of zero-shot prompting and meta-promoting in generating software requirements. The primary tool used was LLaMA3, a large-scale language model hosted on the OLLAMA platform and executed on my personal MacBook.

To facilitate experimentation and data collection, I leveraged a custom pipeline, developed by Dr. Fernando Koch, using Jupyter Notebooks. This allowed me to control the experimental conditions and analyze the results efficiently. Specifically:

* **Zero-Shot Prompting**: I created one notebook where I modified temperature and context parameters to evaluate their impact on prompt generation. This experiment aimed to determine whether adjusting these parameters could improve the quality of generated software requirements.

* **Meta-Prompting**: In a separate notebook, I implemented meta-promoting by running experiments that changed temperature and context parameters. This allowed me to assess how these parameter variations affect the performance of the language model in generating software requirements.

The experimental design involved varying the values of temperature and context parameters within predetermined ranges. For each experiment, I recorded the generated prompts and corresponding requirements responses. To ensure consistency, I used a standardized template for capturing the results and evaluated them using established criteria for requirement quality.

The use of LLaMA3 and Jupyter Notebooks enabled me to conduct controlled experiments, streamline data collection, and facilitate analysis. The custom pipeline allowed me to execute multiple experiments efficiently, which was essential for comprehensively evaluating the effectiveness of zero-shot prompting and meta-promoting in generating software requirements.

By leveraging these tools and techniques, I was able to systematically investigate the impact of temperature and context parameters on prompt generation and requirement quality, providing insights that can inform the development of more effective automated SDLC requirements creation processes. The number of predictions was held constant at 2,000 for the zero-shot trials and held at 1,000 for the meta-prompt initial generation and 5,000 for the meta prompt final response generation.


# Results

This study aimed to investigate the effectiveness of zero-shot prompting and meta-promoting in generating software requirements using LLaMA3. The primary objective was to evaluate the impact of temperature and context parameters on prompt generation and requirement quality.

To achieve this, I conducted a series of experiments using Jupyter Notebooks, modifying temperature and context parameters within predetermined ranges. For each experiment, I recorded the generated prompts and corresponding software requirements, which were then evaluated using established criteria for software requirement quality.

**Performance Evaluation**

To visualize the performance of the language model under different experimental conditions, I created graphs that illustrate the relationship between the temperature/context parameter values and the quality of generated requirements. These visualizations and analyzes are at the bottom of their respective Jupyter notebooks (zero_shot.ipynb and prompt_template.ipynb).

In the zero shot python notebook (zero_shot.ipynb), there is a general trend across the evaluation scores provided by Llama3. They generally increase as temperature increase to 1.66 and then generally begin decreases after that point. Similarily, when analyzing the performance of the zero shot prompts across context size, there is a large jump in performance from 100 to 1000 across all performance metrics. As context size changes from 1000 to 10000, some performance metrics increase and some decrease but the overall performance metrics stay roughly constant. After that point, the overall score and effectiveness score both slightly decrease as the context parameter increases, while the comprehensiveness and relevance scores slightly increase. It appears that increasing the context score past 10000 has varying marginal impacts on performance, with regards to automatically generating requirements for machine learning models.

In the meta prompting python notebook (prompt_template.ipynb), there is a general trend across the evaluation scores provided by Llama3. They generally increase as temperature increase to 1.33 and then marginally increase or decrease across performance metrics. The overall performance has a slight decrease as temperature increases past 1.33. Similarily, when analyzing the performance of the meta prompts across context size, there is a large jump in performance from 100 to 10000 across all performance metrics. After that clarity, relevance and overall performance metrics steadily increases all the way up to 100000, while the comphrensiveness and effectiveness scores decrease. Overall it appears that the higher context levels help the meta prompting framework. 

**Comparison of Results**

The results presented in this section provide insights into the effectiveness of LLaMA3-based prompt generation for software requirements and inform the development of more efficient automated SDLC requirements creation processes.

A comparison of the results from zero-shot prompting and meta-promoting experiments shows that both approaches can generate high-quality software requirements. However, after analyzing the performance it seems to indicate that the optimal temperature/context parameter values for each approach differ. Zero-shot prompting appears to perform better at approx 1.66 temperatures and and lower context levels, while meta-promoting is more effective at 1.33 temperatures and higher context levels.

These findings suggest that the choice of prompting strategy depends on the specific requirements and constraints of the software development project. Other factors outside of performance many need to be researched to determine the best option for an organization to adopt this automated requirement generation approach for machine learning model development.


# Further research

While our research provides valuable insights into prompt engineering and meta-promoting, there are still many open questions and challenges to be addressed. Future research directions could include:

* **Integration with Existing SDLC Tools**: Investigating ways to integrate our prompt generation techniques with existing SDLC tools and platforms.

* **Scalability Evaluation**: Conducting large-scale evaluations of our prompt engineering approach on diverse software projects and domains.

* **User Feedback Mechanisms**: Developing mechanisms for users to provide feedback on the quality of generated prompts, which can help refine our automated requirements creation process.


# Appendix

The following are the scores that were provided by Llama3 in score across Comprehensiveness, Effectiveness, Clarity, Relevance and Overall for the Zero-Shot Trials:

## Zero-Shot Trials Performance

Trial 1    
------------------
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 8
Effectiveness Score: 9
Clarity Score: 8.5
Relevance Score: 9
Overall Score: 8.6
    
Trial 2    
------------------
Temperature: 1.33
Context: 100
------------------
Comprehensiveness Score: 8
Effectiveness Score: 7.5
Clarity Score: 9
Relevance Score: 8.5
Overall Score: 8.1
    
Trial 3    
------------------
Temperature: 1.66
Context: 100
------------------
Comprehensiveness Score: 8
Effectiveness Score: 7
Clarity Score: 9
Relevance Score: 8
Overall Score: 7.8
    
Trial 4    
------------------
Temperature: 1.99
Context: 100
------------------
Comprehensiveness Score: 8
Effectiveness Score: 9
Clarity Score: 9
Relevance Score: 8
Overall Score: 8.5
    
Trial 5    
------------------
Temperature: 1
Context: 1000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 10
Overall Score: 9.5    
    
Trial 6    
------------------
Temperature: 1.33
Context: 1000
------------------
Comprehensiveness Score: 9
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 10
Overall Score: 9.3    
    
Trial 7    
------------------
Temperature: 1.66
Context: 1000
------------------
Comprehensiveness Score: 8.5
Effectiveness Score: 8.5
Clarity Score: 9
Relevance Score: 9
Overall Score: 8.5    
    
Trial 8    
------------------
Temperature: 1.99
Context: 1000
------------------
Comprehensiveness Score: 8
Effectiveness Score: 9
Clarity Score: 9
Relevance Score: 9
Overall Score: 8.5
        
Trial 9    
------------------
Temperature: 1
Context: 10000
------------------
Comprehensiveness Score: 9
Effectiveness Score: 8.5
Clarity Score: 9
Relevance Score: 9
Overall Score: 8.5    
    
Trial 10    
------------------
Temperature: 1.33
Context: 10000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9
Relevance Score: 9.5
Overall Score: 9.2    
    
Trial 11    
------------------
Temperature: 1.66
Context: 10000
------------------
Comprehensiveness Score: 8
Effectiveness Score: 9.5
Clarity Score: 9
Relevance Score: 9
Overall Score: 9.3    
    
Trial 12    
------------------
Temperature: 1.99
Context: 10000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.4
    
Trial 13    
------------------
Temperature: 1
Context: 100000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.4    
    
Trial 14    
------------------
Temperature: 1.33
Context: 100000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9
Relevance Score: 9.5
Overall Score: 9.4    
    
Trial 15    
------------------
Temperature: 1.66
Context: 100000
------------------
Comprehensiveness Score: 9
Effectiveness Score: 8.5
Clarity Score: 9
Relevance Score: 9.5
Overall Score: 8.7    
    
Trial 16    
------------------
Temperature: 1.99
Context: 100000
------------------
Comprehensiveness Score: 8.5
Effectiveness Score: 9
Clarity Score: 9
Relevance Score: 9.5
Overall Score: 8.7


The following are the scores that were provided by Llama3 in score across Comprehensiveness, Effectiveness, Clarity, Relevance and Overall for the Meta-Prompting Trials:
    
## Meta-Prompting Trials Performance
### Tuning the Meta Prompt Generation (additional Prompt Score)

Trial 1    
------------------
Prompt Generating:
Temperature: 1.0
Context: 100
    Prompt Score: 8
    
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 7
Effectiveness Score: 6.5
Clarity Score: 7.5
Relevance Score: 8
Overall Score: 7.2
    
Trial 2    
------------------
Temperature: 1.33
Context: 100
    Prompt Score: 5
        
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 8
Effectiveness Score: 9
Clarity Score: 8.5
Relevance Score: 9
Overall Score: 8.5
    
Trial 3    
------------------
Temperature: 1.66
Context: 100
    Prompt Score: 7
        
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 3
Relevance Score: 2
Overall Score: 2.2
    
Trial 4    
------------------
Temperature: 1.99
Context: 100
    Prompt Score: 9
        
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 2.3
Relevance Score: 3.2
Overall Score: 2.3
    
Trial 5    
------------------
Temperature: 1
Context: 1000
    Prompt Score: 9.3
        
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 5
Effectiveness Score: 6
Clarity Score: 7
Relevance Score: 8
Overall Score: 6.2    
    
Trial 6    
------------------
Temperature: 1.33
Context: 1000
    Prompt Score: 9.1
        
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 3
Relevance Score: 4
Overall Score: 3.3    
    
Trial 7    
------------------
Temperature: 1.66
Context: 1000
    Prompt Score: 9.2
    
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 3
Relevance Score: 3.2
Overall Score: 2.6    
    
Trial 8    
------------------
Temperature: 1.99
Context: 1000
    Prompt Score: 9.5
    
Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 3
Relevance Score: 3.5
Overall Score: 2.7  
        
Trial 9    
------------------
Temperature: 1
Context: 10000
    Prompt Score: 9.4

Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 2
Relevance Score: 2.3
Overall Score: 2     
    
Trial 10    
------------------
Temperature: 1.33
Context: 10000
    Prompt Score: 9.3

Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 2
Relevance Score: 2
Overall Score: 1.8     
    
Trial 11    
------------------
Temperature: 1.66
Context: 10000
    Prompt Score: 9.2

Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 2
Relevance Score: 4
Overall Score: 2.5  
    
Trial 12    
------------------
Temperature: 1.99
Context: 10000
    Prompt Score: 9.6

Final Output:
Temperature: 1.0
Context: 100
------------------
Comprehensiveness Score: 1
Effectiveness Score: 1
Clarity Score: 2
Relevance Score: 3
Overall Score: 2   

### Completed Tuning of Meta Prompt Generation
For the following trials only Temperature of 1.99 and Context of 10000 will be leveraged for the Meta Prompt Generation portion.
    
Trial 13    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.0
Context: 1000
------------------
Comprehensiveness Score: 9
Effectiveness Score: 8.5
Clarity Score: 8.5
Relevance Score: 9
Overall Score: 8.7   
    
Trial 14    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.33
Context: 1000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.3   
    
Trial 15    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.66
Context: 1000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.3   

Trial 16    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.99
Context: 1000
------------------
Comprehensiveness Score: 9
Effectiveness Score: 8.5
Clarity Score: 9
Relevance Score: 9.5
Overall Score: 8.7   
    
Trial 17    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.0
Context: 10000
------------------
Comprehensiveness Score: 9
Effectiveness Score: 8.5
Clarity Score: 8.5
Relevance Score: 9
Overall Score: 8.7   
    
Trial 18    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.33
Context: 10000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9
Relevance Score: 9.5
Overall Score: 9.2   
    
Trial 19    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.66
Context: 10000
------------------
Comprehensiveness Score: 9
Effectiveness Score: 8.5
Clarity Score: 9.5
Relevance Score: 9
Overall Score: 9.1   

Trial 20    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.99
Context: 10000
------------------
Comprehensiveness Score: 9.8
Effectiveness Score: 9.2
Clarity Score: 9.5
Relevance Score: 9.8
Overall Score: 9.5   

Trial 21    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.0
Context: 100000
------------------
Comprehensiveness Score: 8.5
Effectiveness Score: 8
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.2   
    
Trial 22    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.33
Context: 100000
------------------
Comprehensiveness Score: 8.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.2   
    
Trial 23    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.66
Context: 100000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.3 

Trial 24    
------------------
Temperature: 1.99
Context: 10000
------------------
Final Output:
Temperature: 1.99
Context: 100000
------------------
Comprehensiveness Score: 9.5
Effectiveness Score: 9
Clarity Score: 9.5
Relevance Score: 9.5
Overall Score: 9.2 
    