# Workshop: Prompt Engineering and Fine-Tuning for AI Scenarios

## Scenarios

---

### 1. HR Chatbot for CV Review and Feedback
#### System Instructions
- **Role**: The chatbot is an HR specialist with a deep understanding of effective resume writing for various industries.
- **Core Tasks**:
  1. Identify strengths in formatting, skills, and achievements.
  2. Highlight weaknesses or missing elements like quantified results or relevant keywords.
  3. Suggest industry-specific improvements based on the role (e.g., software developer vs. marketing manager).
- **Examples**:
  - **Input**: "Here is my CV. Can you help me improve it?"
  - **Output**: 
    - "Your CV has a clear structure, but your work experience lacks measurable achievements. For example, under 'Software Engineer', consider adding: 'Increased system efficiency by 20% through optimized algorithms.'"
  - **Input**: "Does my CV align with a product manager role?"
  - **Output**: 
    - "For a product manager, consider emphasizing leadership and team collaboration. Add bullet points under your experience like: 'Led cross-functional teams of 10+ members to deliver product launches on schedule.'"

#### Fine-Tuning Process
1. **Dataset**:
   - Collect anonymized CVs, job descriptions, and feedback from HR professionals.
   - Include CVs tailored for various industries to cover diverse scenarios.
2. **Preprocessing**:
   - Standardize sections like "Education", "Work Experience", and "Skills" for uniformity.
   - Annotate data to match job requirements with CV content (e.g., identifying keyword gaps).
3. **Model Tuning**:
   - Train the model on labeled CV-feedback pairs.
   - Include job descriptions to teach role-specific suggestions.
4. **Testing**:
   - Validate the chatbot with actual CVs and compare its feedback to HR expert reviews.

#### Challenges & Solutions
- **Challenge**: Handling non-standard CV formats (e.g., graphical resumes).
  - **Solution**: Use text extraction tools (e.g., OCR) to preprocess such formats.
- **Challenge**: Overgeneralizing suggestions.
  - **Solution**: Incorporate job-specific datasets during fine-tuning.

#### Future Enhancements
- Integrate AI to analyze online job postings and suggest matching CV edits.
- Enable upload of LinkedIn profiles for tailored improvements.

---

### 2. Teacher Assistant Chatbot for Full-Stack Development
#### System Instructions
- **Role**: The chatbot is a full-stack programming tutor specializing in JavaScript, React, Node.js, and databases.
- **Core Tasks**:
  1. Explain complex concepts in simple terms (e.g., "What is the DOM?").
  2. Provide code reviews with feedback on syntax, logic, and optimization.
  3. Solve common coding problems, such as debugging or designing algorithms.
- **Examples**:
  - **Input**: "Explain how React's lifecycle methods work."
  - **Output**: 
    - "React's lifecycle methods are functions that get triggered during specific stages of a component's existence. For example, 'componentDidMount' runs after the component is added to the DOM."
  - **Input**: "Here's my code. Why is it throwing an error?"
  - **Code**:
    ```javascript
    const [count, setCount] = useState(0);
    useEffect(() => {
      setCount(count + 1);
    }, []);
    ```
  - **Output**:
    - "Your `useEffect` dependency array is empty, but you're using `count`. This will cause the effect to only run once, leading to a stale state. Add `count` to the dependency array."

#### Fine-Tuning Process
1. **Dataset**:
   - Collect explanations of programming concepts, annotated coding examples, and debugging case studies.
   - Include Q&A threads from forums like Stack Overflow.
2. **Preprocessing**:
   - Categorize the dataset by topic (e.g., React, JavaScript, databases).
   - Annotate with levels of difficulty (beginner, intermediate, advanced).
3. **Model Tuning**:
   - Train the model to explain, debug, and review code with step-by-step solutions.
4. **Testing**:
   - Evaluate the model by having it assist in solving real coding challenges from platforms like LeetCode or HackerRank.

#### Challenges & Solutions
- **Challenge**: Explaining advanced concepts to beginners.
  - **Solution**: Add multiple versions of explanations (e.g., analogies for beginners, technical definitions for experts).
- **Challenge**: Recognizing incorrect code logic.
  - **Solution**: Train the model with datasets emphasizing logical errors and fixes.

#### Future Enhancements
- Enable interactive coding sessions where users can run and debug code in real time.
- Incorporate voice commands for easier interaction during hands-on coding.

---

### 3. Medical Assistant Chatbot
#### System Instructions
- **Role**: The chatbot provides basic health advice and triages medical queries, adhering to ethical and privacy standards.
- **Core Tasks**:
  1. Recognize common symptoms and offer general advice.
  2. Refer urgent or complex cases to healthcare professionals.
  3. Provide preventive health tips (e.g., diet, exercise).
- **Examples**:
  - **Input**: "I have a sore throat and fever. What should I do?"
  - **Output**: 
    - "It sounds like you might have a viral infection. Stay hydrated, take over-the-counter fever reducers, and consult a doctor if symptoms worsen."
  - **Input**: "Can you diagnose this rash?"
  - **Output**: 
    - "I'm unable to diagnose rashes. Please consult a dermatologist for a proper evaluation."

#### Fine-Tuning Process
1. **Dataset**:
   - Use publicly available medical FAQs, symptom checkers, and health articles.
   - Exclude datasets involving deep diagnostic reasoning or sensitive data.
2. **Preprocessing**:
   - Normalize input to focus on general health topics (e.g., "sore throat remedies").
   - Annotate ethical boundaries (e.g., when to defer cases).
3. **Model Tuning**:
   - Train on datasets labeled for advice vs. escalation scenarios.
4. **Testing**:
   - Simulate user queries and evaluate against standard medical guidelines.

#### Challenges & Solutions
- **Challenge**: Avoiding overstepping into diagnosis.
  - **Solution**: Implement strict filters to escalate ambiguous cases.
- **Challenge**: Ensuring culturally appropriate advice for global users.
  - **Solution**: Include datasets from diverse regions and demographics.

#### Future Enhancements
- Connect to wearable devices for personalized health insights.
- Support mental health queries with links to resources and hotlines.