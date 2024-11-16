# Prompt Engineering Fundamentals

How you write your prompt to the LLM matters, a carefully crafted prompt can achieve a better result than one that isn't. 

## What is Prompt Engineering?

We started this lesson by defining **Prompt Engineering** as the process of _designing and optimizing_ text inputs (prompts) to deliver consistent and quality responses (completions) for a given application objective and model. We can think of this as a 2-step process:

- _designing_ the initial prompt for a given model and objective
- _refining_ the prompt iteratively to improve the quality of the response

This is necessarily a trial-and-error process that requires user intuition and effort to get optimal results. So why is it important? To answer that question, we first need to understand three concepts:

- _Tokenization_ = how the model "sees" the prompt
- _Base LLMs_ = how the foundation model "processes" a prompt
- _Instruction-Tuned LLMs_ = how the model can now see "tasks"

### Tokenization

An LLM sees prompts as a _sequence of tokens_ where different models (or versions of a model) can tokenize the same prompt in different ways. Since LLMs are trained on tokens (and not on raw text), the way prompts get tokenized has a direct impact on the quality of the generated response.


## Why do we need Prompt Engineering?


1. **Model responses are stochastic.**
   
1. **Models can fabricate responses.** 

1. **Models capabilities will vary.** 


- Use the same prompt with different LLM deployments (e.g, OpenAI, Gemini, Microsoft Co-Pilot) - did you see the variations?
- Use the same prompt repeatedly with the _same_ LLM deployment (e.g., Azure OpenAI playground) - how did these variations differ?

## Prompt Construction

We've seen why prompt engineering is important - now let's understand how prompts are _constructed_ so we can evaluate different techniques for more effective prompt design.

### Basic Prompt

### Complex Prompt

### Instruction Prompt

- an instruction (action)
- relevant content (that influences action)

### Using Examples

This is an approach where you use the primary content to "feed the model" some examples of the desired output for a given instruction, and let it infer the pattern for the desired output. Based on the number of examples provided, we can have zero-shot prompting, one-shot prompting, few-shot prompting etc.

The prompt now consists of three components:

- A task description
- A few examples of the desired output
- The start of a new example (which becomes an implicit task description)


| Learning Type | Prompt (Input) | Completion (Output) |
|:---|:---|:---|
| Zero-shot  | "The Sun is Shining". Translate to Spanish  | "El Sol está brillando".|
| One-shot | "The Sun is Shining" => ""El Sol está brillando". <br> "It's a Cold and Windy Day" => | "Es un día frío y ventoso". |
| Few-shot | The player ran the bases => Baseball  <br/> The player hit an ace => Tennis  <br/> The player hit a six => Cricket  <br/> The player made a slam-dunk => | Basketball |
| | | |


Note how we had to provide explicit instruction ("Translate to Spanish") in zero-shot prompting, but it gets inferred in the one-shot prompting example. The few-shot example shows how adding more examples allows models to make more accurate inferences with no added instructions.

### Prompt Cues

Another technique for using primary content is to provide _cues_ rather than examples. In this case, we are giving the model a nudge in the right direction by _starting it off_ with a snippet that reflects the desired response format. The model then "takes the cue" to continue in that vein.


| Number of Cues | Prompt (Input) | Completion (Output) |
|:---|:---|:---|
| 0  | Jupiter is the fifth planet from the Sun and the largest in the Solar System. It is a gas giant with a mass one-thousandth that of the Sun, but two-and-a-half times that of all the other planets in the Solar System combined. Jupiter is one of the brightest objects visible to the naked eye in the night sky, and has been known to ancient civilizations since before recorded history.  <br/>**Summarize This**  | Jupiter is the largest planet in our Solar System and the fifth one from the Sun. It is a gas giant with a mass 1/1000th of the Sun's, but it is heavier than all the other planets combined. Ancient civilizations have known about Jupiter for a long time, and it is easily visible in the night sky..|
| 1 | Jupiter is the fifth planet from the Sun and the largest in the Solar System. It is a gas giant with a mass one-thousandth that of the Sun, but two-and-a-half times that of all the other planets in the Solar System combined. Jupiter is one of the brightest objects visible to the naked eye in the night sky, and has been known to ancient civilizations since before recorded history.  <br/>**Summarize This** <br/> What we learned is that Jupiter | is the fifth planet from the Sun and the largest in the Solar System. It is a gas giant with a mass one-thousandth that of the Sun, but two-and-a-half times that of all the other planets combined. It is easily visible to the naked eye and has been known since ancient times. |
| 2 | Jupiter is the fifth planet from the Sun and the largest in the Solar System. It is a gas giant with a mass one-thousandth that of the Sun, but two-and-a-half times that of all the other planets in the Solar System combined. Jupiter is one of the brightest objects visible to the naked eye in the night sky, and has been known to ancient civilizations since before recorded history.  <br/>**Summarize This** <br/> Top 3 Facts We Learned: | 1. Jupiter is the fifth planet from the Sun and the largest in the Solar System. <br/> 2. It is a gas giant with a mass one-thousandth that of the Sun...<br/> 3. Jupiter has been visible to the naked eye since ancient times ... |
| | | |


### Prompt Templates

A prompt template is a _pre-defined recipe for a prompt_ that can be stored and reused as needed, to drive more consistent user experiences at scale.


## Prompting Best Practices

Now that we know how prompts can be _constructed_, we can start thinking about how to _design_ them to reflect best practices. We can think about this in two parts - having the right _mindset_ and applying the right _techniques_.

### Prompt Engineering Mindset

Prompt Engineering is a trial-and-error process so keep three broad guiding factors in mind:

1. **Domain Understanding Matters.** 
2. **Model Understanding Matters.**
3. **Iteration & Validation Matters.**

## Knowledge check

Which of the following is a good prompt following some reasonable best practices?

1. Show me an image of red car
2. Show me an image of red car of make Volvo and model XC90 parked by a cliff with the sun setting
3. Show me an image of red car of make Volvo and model XC90 

A: 2, it's the best prompt as it provides details on "what" and goes into specifics (not just any car but a specific make and model) and it also describes the overall setting. 3 is next best as it also contains a lot of description.


## Great Work! Continue Your Learning

Want to learn more about different Prompt Engineering concepts? Go to the [contiuned learning page](../13-continued-learning/README.md?WT.mc_id=academic-105485-koreyst) to find other great resources on this topic.

Head over to Lesson 5 where we will look at [advance prompting techniques](../05-advanced-prompts/README.md?WT.mc_id=academic-105485-koreyst)!
