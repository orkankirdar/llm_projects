# llm_projects
import openai
system_prompt = "You are helpful assistant that generates short and relevant email subject lines based on the content of the email."
user_prompt = """
    Hi Sarah,
    
    I hope you're doing well. I wanted to update you on the marketing campaign we're working on. We've completed the initial phase, including the target audience research and content creation. Now we are moving on to the testing phase and expect to have the first set of results by the end of this week.
    
    I'll be happy to discuss the next steps with you during our meeting scheduled for Friday. Let me know if you have any questions or suggestions.
    
    Best,
    Emily
"""

messages = [
    {"role" : "system" , "content" : system_prompt},
    {"role" : "user" , "content" : user_prompt}
] 


response = openai.chat.completions.create(
    model = "gpt-4o-mini",
    messages = messages
)


print(response.choices[0].message.content)
