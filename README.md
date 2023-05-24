# SQLprompter
 This is a Jupyter Notebook for generating SQL queries based on user questions both in French and English using the OpenAI API. It provides a Gradio interface for users to input their questions and receive the corresponding SQL query as output.

## Usage
To use this code, you need to have an OpenAI API key. You can sign up for an API key on the OpenAI website.

1. Open the Jupyter Notebook file (database_prompter.ipynb) in Jupyter Notebook or JupyterLab.
2. Make sure you have the necessary dependencies installed. You can install them using the following command: !pip install gradio openai.
3. Set up your OpenAI API credentials by replacing "YOUR_API_KEY" with your actual API key in the code cell.
4. Run the code cells in the notebook sequentially.
5. The Gradio interface will be displayed with an input text field.
6. Enter your question in the text input field and press Enter.
7. The SQL query corresponding to your question will be displayed below.

## Example
Here is an example of how the prompt can be defined:

```SQL
prompt = """
Write a SQL query that retrieves the total sales for each product category from the 'sales' table.

---

Table Schema:

sales
- id: integer
- product_id: integer
- quantity: integer
- price: float
- timestamp: timestamp

---

Example Usage:

User: "What is the total sales for each product category?"
SQL Query: "SELECT category, SUM(quantity * price) AS total_sales FROM products JOIN sales ON products.id = sales.product_id GROUP BY category;"

---

User: "Which product category has the highest total sales?"
SQL Query: "SELECT category, SUM(quantity * price) AS total_sales FROM products JOIN sales ON products.id = sales.product_id GROUP BY category ORDER BY total_sales DESC LIMIT 1;"
"""

```

## Dependencies
gradio: For creating the user interface.

openai: The OpenAI Python library for making API requests.

## Colab Demo
For a live demonstration of the code, you can run it in a Colab notebook. Please follow the steps below:

1. Go to Google Colab.
2. Click on File -> Open Notebook.
3. Select the GitHub tab.
4. Enter the URL of this GitHub repository ([SQLprompter](https://github.com/LeHaroun/SQLprompter)) in the Enter a GitHub URL or search by organization or user field.
5. Press Enter, and the repository will load in Colab.
6. Open the notebook file (database_prompter.ipynb) and follow the instructions inside to run the code.

## Contributions
Contributions are welcome! If you find any issues or want to add new features, please feel free to submit a pull request.

## License
This code is licensed under the MIT License.
