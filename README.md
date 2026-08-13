# Near-Real-Time Payments Reconciliation — PySpark + Delta Lake

## Stack
- Python
- PySpark
- Delta Lake
- Spark SQL for serving/analytics

The assignment explicitly permits **Option B: PySpark + Delta Lake (local or Databricks Community)**.

## Repository
```text
.
├── FileStore/payments_reconciliation/
│   ├── bronze
│   ├── data
│   ├── dq_reconciliation
│   ├── gold_reconciled_transactions
│   ├── visual_screenshots
├── Payments_Reconciliation.ipynb
├── README.md
```

## Run locally
Prerequisites: Create Databricks Free Edition account and start running Payments_Reconciliation.ipynb file code

Delta tables are written under `FileStore/payments_reconciliation/`:
- `bronze`
- `data`
- `dq_reconciliation`
- `gold_reconciled_transactions`

Tests cover matched transactions, amount mismatches above ₹1 and missing settlements.

## Databricks Free Edition
Upload the repository to Databricks, install `delta-spark`/use the runtime's built-in Delta support, and execute the same Python entry point or split the modules into notebook cells. Replace local paths with DBFS/Volumes paths as available in the environment.

## Production changes
For production, I would add:
- Kafka Structured Streaming for ledger/UPI events.
- Auto Loader or equivalent for cloud object-store settlement files.
- Delta checkpointing/watermarks for streaming.
- Cloud IAM and secrets manager integration.
- Great Expectations/Deequ or equivalent for richer DQ.
- CI/CD with unit + integration tests.
- Delta OPTIMIZE/compaction and retention policies.

## Important data note
The repository contains the sample `transactions.csv`, `settlements.csv`, and `upi_responses.json` files that were available with the assignment package.
