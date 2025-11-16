# spongent
A agent to find and recommend videos

# 🤖 ACG Keyword Searcher (V0.1 - Single File Version)

This is a **single-file** Python script representing the **V0.1 Proof of Concept** for my "ACG Semantic Search AI Agent" project.

This version **does not contain any AI or Large Language Models (LLMs)**. It is a local, terminal-based **keyword search engine**.

For maximum simplicity, this version combines the **Data (Database) and Logic (Search) into one single file**.

---

## 🎯 V0.1 Goals

* **Simplicity:** Keep all code (data and logic) in one file (`search_v0_1.py`) for rapid prototyping.
* **Implement Core Function:** Achieve a simple keyword-matching search using basic Python (lists, dictionaries, and loops).
* **Validate the Idea:** Prove that fetching data from a "database" based on user input is feasible.
* **Build a Foundation:** Serve as the foundation for V0.6 (the first Agent) and V1.0 (the semantic search version).

---

## 🛠️ Tech Stack

* **Python 3** (That's it!)

---

## 📂 File Structure

acg-search-project/ │ 
├── 📄 search_v0_1.py # (Data AND Search Logic are all in this one file!) 
└── 📄 README.md # (The file you are reading)


### `search_v0_1.py` Internal Structure

This file contains both the database and the search logic.

```python
# search_v0_1.py

# --- 1. The Data (DATABASE) ---
# The database is hard-coded at the top of the script
DATABASE = [
    {
        "title": "Steins;Gate",
        "plot": "A... university student... invents... a time machine..."
    },
    {
        "title": "Fullmetal Alchemist: Brotherhood",
        "plot": "Two brothers... used forbidden human transmutation..."
    }
    # ... you can manually add more here ...
]

# --- 2. The Logic (FUNCTION) ---
def find_acg(search_keyword):
    """
    Loops through the DATABASE, searching for the keyword.
    """
    found_results = []
    for entry in DATABASE:
        # Check plot and title, ignoring case
        if search_keyword.lower() in entry['plot'].lower() or \
           search_keyword.lower() in entry['title'].lower():
            found_results.append(entry['title'])
    return found_results

# --- 3. The Execution (MAIN) ---
# The main entry point for the script
if __name__ == "__main__":
    user_query = input("Please enter a plot keyword to search for: ")
    results = find_acg(user_query)
    
    if results:
        print("\n✅ Found results! See below:")
        for title in results:
            print(f"  - {title}")
    else:
        print(f"\n❌ Sorry, no entries found containing '{user_query}'.")

▶️ How to Run
Ensure you have Python 3 installed.

Create a file named search_v0_1.py and copy the code example above into it.

Open your terminal (Command Prompt).

Run the search_v0_1.py script:

Bash

python search_v0_1.py
💡 Demo
When you run the script, the terminal will show:

Please enter a plot keyword to search for: alchemy
You type alchemy and press Enter. It will output:

✅ Found results! See below:
  - Fullmetal Alchemist: Brotherhood
🔮 Next Steps
V0.6: Introduce LangChain and Streamlit to upgrade this script into a true AI Agent with a web interface.

V1.0: Introduce ChromaDB and "semantic embeddings" to enable true "AI semantic search"
