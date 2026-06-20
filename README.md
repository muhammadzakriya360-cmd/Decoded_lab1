# Decoded_lab1

# KNOWLEDGE BASE — The Brain of the Chatbot

knowledge_base = {
    # --- Greetings ---
    "hello"        : "Hello! I'm DecoBot 🤖 — your AI assistant. How can I help you today?",
    "hi"           : "Hi there! 👋 What can I do for you?",
    "hey"          : "Hey! Great to see you. What's on your mind?",
    "good morning" : "Good morning! ☀️ Hope you have a productive day!",
    "good evening" : "Good evening! 🌙 How can I assist you tonight?",

    # --- Identity ---
    "who are you"  : "I am DecoBot 🤖, a rule-based AI chatbot built for DecodeLabs Project 1.",
    "what are you" : "I am a Rule-Based AI — I respond using predefined logic, not machine learning.",
    "your name"    : "My name is DecoBot! Built with Python logic at DecodeLabs. 🚀",

    # --- AI Knowledge ---
    "what is ai"         : "AI stands for Artificial Intelligence — machines designed to simulate human thinking and decision-making.",
    "what is machine learning" : "Machine Learning is a subset of AI where systems learn from data instead of explicit rules.",
    "what is deep learning"    : "Deep Learning uses neural networks with many layers to learn complex patterns from large datasets.",
    "difference between ai and ml" : "AI is the broad concept; ML is a specific approach to achieve AI using data-driven learning.",

    # --- DecodeLabs ---
    "what is decodelabs" : "DecodeLabs is an industrial training platform that helps students build real AI projects. 💡",
    "tell me about this project" : "This is Project 1 of the DecodeLabs AI Internship — building a Rule-Based Chatbot using control flow and logic.",

    # --- Python Help ---
    "what is a dictionary" : "A Python dictionary stores key-value pairs for O(1) constant-time lookup — much faster than if-elif chains!",
    "what is a loop"       : "A loop repeats a block of code. `while True` creates an infinite loop that runs until a break condition is met.",
    "what is sanitization" : "Input sanitization means cleaning user input using `.lower().strip()` to handle uppercase, spaces, and typos.",

    # --- Fun / Small Talk ---
    "how are you"  : "I'm running perfectly — all logic gates are green! 🟢 How about you?",
    "tell me a joke" : "Why do programmers prefer dark mode? Because light attracts bugs! 🐛😄",
    "what can you do" : "I can answer questions about AI, Python, DecodeLabs, and general topics. Try asking me something!",
    "thank you"    : "You're welcome! 😊 Keep learning and keep building!",
    "thanks"       : "Anytime! 🙌 That's what I'm here for.",

    # --- Exit Commands ---
    "bye"          : "__EXIT__",
    "exit"         : "__EXIT__",
    "quit"         : "__EXIT__",
    "goodbye"      : "__EXIT__",
}

# PHASE 1 — INPUT: Sanitization & Normalization
# Converts 'HeLLo  ' → 'hello'
def sanitize_input(raw_input):
    """
    Cleans user input:
    - .lower()  → removes case sensitivity
    - .strip()  → removes leading/trailing whitespace
    """
    return raw_input.lower().strip()



# PHASE 2 — PROCESS: Intent Matching

def get_response(clean_input):
    """
    Looks up the cleaned input in the knowledge base.
    Returns the matched response or a default fallback message.
    """
    fallback = "🤔 I don't understand that yet. Try asking about AI, Python, or type 'what can you do'."
    return knowledge_base.get(clean_input, fallback)



# PHASE 3 — OUTPUT: Response Generation
# Prints the bot's reply to the user

def display_response(response):
    print(f"\n🤖 DecoBot: {response}\n")
    print("-" * 50)
    
# MAIN ENGINE — The Heartbeat (Infinite Loop)
# Runs continuously until user types exit/bye/quit

def run_chatbot():
    print("=" * 50)
    print("   🤖 DecoBot — Rule-Based AI Chatbot")
    print("   DecodeLabs | Batch 2026")
    print("=" * 50)
    print("💬 Start chatting! Type 'bye' or 'exit' to quit.")
    print("-" * 50)

    # THE HEARTBEAT — Infinite loop (stays alive until kill command)
    while True:

        #PHASE 1: INPUT
        raw_input = input("You: ")

        clean_input = sanitize_input(raw_input)


        if clean_input == "":
            print("⚠️  Please type something!")
            continue

        # PHASE 2: PROCESS
        response = get_response(clean_input)

        if response == "__EXIT__":
            print("\n🤖 DecoBot: Goodbye! Thanks for chatting. Keep building! 🚀")
            print("=" * 50)
            break

        #PHASE 3: OUTPUT
        display_response(response)


run_chatbot()
