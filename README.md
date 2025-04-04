# SQLDeps Web Application

An interactive web interface for extracting SQL dependencies using Large Language Models.

## What is this?

This web application is a Streamlit-based showcase for [SQLDeps](https://github.com/glue-lab/sqldeps),
allowing users to interactively explore how large language models can analyze SQL queries and extract
their underlying table and column dependencies.

## Features

- 🔍 Instantly visualize SQL query dependencies
- 🤖 Powered by advanced language models
- 📊 Interactive, real-time dependency extraction
- 💾 Optional database schema validation

## Example

Consider this SQL query:

```sql
WITH user_orders AS (
    SELECT o.user_id, COUNT(*) AS order_count 
    FROM orders o 
    JOIN users u ON o.user_id = u.id 
    WHERE u.status = 'active' 
    GROUP BY o.user_id
)
CREATE TABLE transactions.user_order_summary AS 
SELECT * FROM user_orders;
```

When processed, the application shall return:
- Dependencies: `orders` and `users` tables
- Used columns: `user_id`, `status`
- Output: `transactions.user_order_summary` table

## Live Demo

[Try SQLDeps Web Application](https://sqldeps.streamlit.app)

## API Key Limitations

This web application provides complimentary API access to:
- OpenAI
- Groq
- DeepSeek

Due to the showcase nature of this service, we offer a **limited number of free requests**. If the service becomes temporarily unavailable or unresponsive, this may be due to exhausted API credits.

For unlimited or production use, we recommend:
- Setting up your own API keys
- Exploring the [SQLDeps library](https://github.com/glue-lab/sqldeps)

## Open Source

Part of the [SQLDeps](https://github.com/glue-lab/sqldeps) project,
demonstrating the power of AI in understanding SQL dependencies.

## License

MIT License
