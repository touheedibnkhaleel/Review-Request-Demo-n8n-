# Review-Request-Demo (n8n)

A small n8n workflow that asks a customer for a review 7 days
after they bought a product. Built as a demo for online stores.

## How it works
1. Schedule Trigger runs every day at 9am
2. Google Sheets reads the order list
3. IF node keeps orders placed exactly 7 days ago with an empty review_status
4. Gmail sends the review request email
5. Google Sheets writes "review requested on <date>" to review_status,
   so the customer is never asked twice

## Sheet format
order_date | customer_name | customer_email | product | order_status | review_status
(order_date as plain text, yyyy-MM-dd)

## Setup
1. Import `review-request-workflow.json` into n8n
2. Connect your own Google Sheets and Gmail credentials
3. Point the sheet nodes at your own Google Sheet
4. Replace the store link in the email

## Related
Works alongside the reorder reminder demo on the same sheet:
it only writes to the review_status column.

## Note
This is a demo with test data, not a client project.
