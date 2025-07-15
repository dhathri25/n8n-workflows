# 🔁 n8n Workflow: Order Data Pipeline with Airtable & HTTP Integration

This repository contains an **n8n automation workflow** that performs order validation, conditional data routing, and integration with **Airtable** and a **custom webhook endpoint**. It’s ideal for beginner to intermediate n8n users working with e-commerce, CRM, or internal order management systems.

## 📂 Workflow File

- [`My workflow 2.json`](./My%20workflow%202.json)

## 🚀 Workflow Summary

This workflow includes the following steps:

1. **Manual Trigger** – Start the workflow manually from the n8n editor.
2. **HTTP Request** – Sends a POST/GET request to a custom webhook (`https://internal.users.n8n.cloud/webhook/custom-erp`) with a `unique_id` header for authentication.
3. **IF Node** – Evaluates a condition on `orderStatus` (e.g., filters specific order types).
4. **Set Node ("Edit Fields")** – Manually assigns values to variables like `orderID` and `customerID`.
5. **Code Node** – Uses custom JavaScript to compute:
   - `totalBooked`: total number of items
   - `bookedSum`: sum of all `orderPrice` values
6. **Airtable Node** – Retrieves schema details of a specific Airtable base (e.g., for further processing or schema validation).

## 🔧 Technologies Used

- [n8n.io](https://n8n.io/)
- HTTP Request Node
- JavaScript Code Node
- Airtable API (via Airtable Personal Access Token)

## 📸 Visual Flow

> *(Optional: Add a screenshot of your workflow here)*

## 📥 How to Use

1. Open n8n and go to **Import Workflow**.
2. Upload `My workflow 2.json`.
3. Update node credentials:
   - Set your own `httpHeaderAuth` for the HTTP Request node.
   - Provide an Airtable token and base ID.
4. Run using the **manual trigger**.

## 📌 Notes

- Make sure your input JSON contains fields like `orderPrice` and `orderStatus` for proper condition checks.
- This is a **template-level workflow** – you can expand it with additional logic or database actions.

---

🧠 **Use this as a starter to build custom order processing or CRM sync automations!**

