# Do LLMs Have Distinct and Consistent Personality? TRAIT: Personality Testset designed for LLMs with Psychometrics

The paper “Do LLMs Have Distinct and Consistent Personality? TRAIT: Personality Testset designed for LLMs with Psychometrics” introduces a novel psychometric tool called TRAIT to assess the personality of large language models (LLMs). The psychometric, statistical, and evaluation methods used in the paper are essential for ensuring that TRAIT can effectively and reliably measure personality traits in LLMs. Here’s a breakdown of these methods:

## Psychometric Methods

Psychometrics involves the theory and techniques of psychological measurement, including the measurement of knowledge, abilities, attitudes, and personality traits. In this paper, the psychometric focus is on personality traits, specifically leveraging validated human personality frameworks such as the **Big Five Inventory (BFI)** and the **Short Dark Triad (SD-3)**.

1. **Use of Established Personality Models**:
   - **Big Five Inventory (BFI)**: This model assesses five key dimensions of personality: openness, conscientiousness, extraversion, agreeableness, and neuroticism. These are well-established in psychology for their robust ability to categorize human personality traits.
   - **Short Dark Triad (SD-3)**: This model captures three socially undesirable traits: psychopathy, Machiavellianism, and narcissism.

   **Example**: The TRAIT test integrates questions from both the BFI and SD-3 to ensure that it comprehensively covers both positive and negative personality traits in LLMs. For instance, BFI might assess traits like "openness to new experiences" with questions like "I am full of ideas," while SD-3 evaluates manipulativeness or empathy deficiencies with prompts like "I tend to manipulate others to get my way."

2. **Scenario-based Personality Measurement**:
   Instead of using direct self-assessment, TRAIT employs **scenario-based questions** to evaluate personality traits. These scenarios are generated using the **ATOMIC10x knowledge graph**, a large commonsense knowledge base that provides contextually rich situations where personality traits might manifest.

   **Example**: A scenario like "You are walking with a group of friends, and one suggests an idea you disagree with. Do you: (1) Assertively state your opposing view, (2) Passively go along, etc." could assess assertiveness or agreeableness in a specific context. This method contrasts with traditional self-assessment methods that simply ask, "Are you assertive?"

## Statistical Methods

To ensure the reliability and validity of TRAIT, the authors apply several statistical methods and metrics commonly used in psychometric assessments:

1. **Validity**: This refers to the extent to which a test measures what it purports to measure. In the paper, **refusal rate** is used as a key indicator of validity. This metric measures how often the LLMs refuse to answer a question or provide non-responses.

   **Example**: A high refusal rate would indicate that the questions are not valid for measuring the intended traits in LLMs because the models are unable or unwilling to provide a meaningful answer. TRAIT showed an extremely low refusal rate (0.2%), implying high validity.

2. **Reliability**: The consistency of the test results over different conditions or repeated trials. The paper assesses three reliability metrics:
   - **Prompt Sensitivity**: Measures the variability in LLM responses when slightly different versions of the same prompt are used. A high sensitivity would indicate low reliability, as it would mean that small changes in phrasing lead to different results.
   - **Option Order Sensitivity**: Evaluates how the order of multiple-choice options affects the LLM's responses. Ideally, changing the order of answer options should not affect the chosen answer.
   - **Paraphrase Sensitivity**: Tests whether the same answer is given to a question phrased in different ways.

   **Example**: If a model rates itself as highly extraverted when asked, "Do you enjoy being around people?" but responds differently to "Do you find social situations energizing?" the model exhibits high paraphrase sensitivity, indicating lower reliability.

3. **Test-Retest Reliability**: This psychometric concept is used to check if a test consistently produces the same results over repeated trials. While the paper does not use a traditional test-retest design, the metrics like prompt and option sensitivity mimic this by slightly altering the test conditions and checking if the responses remain consistent.

4. **Parallel-Form Reliability**: This involves administering different versions of the same test and correlating the results. In the paper, the authors introduce **paraphrase sensitivity** as a parallel-form reliability metric, assessing how similar LLM responses are when asked the same question using different phrasings.

   **Example**: TRAIT generated paraphrased versions of the same question (e.g., "Do you like meeting new people?" vs. "Do you enjoy socializing with strangers?"). If the model provides consistent answers, it indicates high parallel-form reliability.

5. **Statistical Comparisons Across Models**:
   - The paper provides statistical comparisons of the personality traits across different LLMs (e.g., GPT-4, GPT-3.5, Mistral, Llama models) to highlight distinctiveness and consistency in behavior.
   - **Confidence Intervals**: The results include confidence intervals to ensure that the differences observed between models are statistically significant.
   - **Mean and Standard Deviation**: For each trait, the authors compute the mean personality score and standard deviation across the tested LLMs. This allows for an analysis of how much variation exists between the models for each personality trait.

   **Example**: The study found that GPT-4 had a statistically significant higher agreeableness score than GPT-3.5, indicating a consistent personality difference that may be due to their differing training data or alignment processes.

## Evaluation Methods

The evaluation of the LLMs’ personality through TRAIT involves scoring their responses across different personality traits and then assessing the **distinctiveness**, **consistency**, and **alignment** of these traits.

1. **TRAIT Scoring System**:
   The LLMs are evaluated based on their answers to a set of 8,000 multiple-choice questions. Each answer is associated with a score that reflects high or low levels of a given personality trait (e.g., high agreeableness or low extraversion).

   **Example**: The model's response to a scenario about helping others could be scored as high in agreeableness if it chooses options like “I offer my help even if it's inconvenient for me," and low if it picks “I avoid getting involved unless necessary."

2. **Comparison to Human Benchmarks**: The results of the TRAIT test are compared to human assessments, providing a benchmark for evaluating the relative levels of traits in LLMs versus humans.

   **Example**: The authors noted that aligned models like GPT-4 scored similarly to human teaching assistants, who tend to be high in agreeableness and conscientiousness but lower in openness and extraversion.

3. **Correlation Analysis**:
   The paper explores correlations between personality traits in LLMs, using **intercorrelation matrices** to compare how certain traits are related to one another (e.g., high extraversion might correlate with high agreeableness). This is akin to psychometric methods used in human personality testing.

   **Example**: The study found a negative correlation between agreeableness and dark triad traits like Machiavellianism and psychopathy, which is consistent with findings in human personality research.

4. **Prompting Techniques**: The paper evaluates how effective prompting is in eliciting specific personality traits in LLMs. Different prompts are used to induce behaviors aligned with certain traits (e.g., high conscientiousness or low extraversion), and the effectiveness of these prompts is measured.

   **Example**: Prompts were less effective in eliciting high psychopathy or low conscientiousness, which the authors attribute to the alignment processes that are designed to suppress undesirable traits in LLMs.

## Summary of Evaluation Metrics

| Metric                     | Definition & Use                                                         | Key Findings                                      |
|----------------------------|--------------------------------------------------------------------------|---------------------------------------------------|
| **Refusal Rate**           | Measures how often the model refuses to answer a question.               | TRAIT had a refusal rate of only 0.2%, indicating high validity. |
| **Prompt Sensitivity**     | Checks if small changes in prompt wording lead to different responses.   | TRAIT showed lower sensitivity compared to other tests. |
| **Option Order Sensitivity**| Evaluates if the order of options affects model responses.               | Low sensitivity indicates robust evaluation in TRAIT. |
| **Paraphrase Sensitivity** | Assesses if different phrasings of the same question produce consistent answers. | TRAIT had lower paraphrase sensitivity compared to other tests, meaning it was more reliable. |
| **Personality Trait Scores**| Evaluates LLMs across eight traits from the Big Five and Dark Triad models. | LLMs showed distinct personality traits, with GPT-4 scoring high on agreeableness and conscientiousness. |
| **Option Order Sensitivity**| Evaluates if the order of options affects model responses.               | Low sensitivity indicates robust evaluation in TRAIT. |
| **Paraphrase Sensitivity**  | Assesses if different phrasings of the same question produce consistent answers. | TRAIT had lower paraphrase sensitivity compared to other tests, meaning it was more reliable. |
| **Personality Trait Scores**| Evaluates LLMs across eight traits from the Big Five and Dark Triad models. | LLMs showed distinct personality traits, with GPT-4 scoring high on agreeableness and conscientiousness. |

In conclusion, the paper uses a combination of psychometric tools, reliability and validity metrics, and statistical comparisons to rigorously evaluate the personality traits of LLMs. This method provides a more nuanced and reliable framework for assessing AI behavior, especially compared to prior self-assessment-based approaches.
