# Documentation Screenshots & Architecture Diagrams Catalog

This folder contains all visual assets, architecture diagrams, AWS console screenshots, database schemas, HR portal views, and sample output artifacts extracted from the **AWS Automatic Payroll Processing & Payslip Delivery Engine** documentation report (`Automatic_Payroll_Processing_Final_Documentation_FINAL (1).pdf`).

---

## 📸 Asset Inventory & References

### 1. System Architecture
| File Name | Description | Source Section |
| :--- | :--- | :--- |
| [`architecture-diagram.png`](./architecture-diagram.png) | End-to-End Event-Driven AWS Serverless Architecture Diagram | Section 4.1 / Appendix A |

### 2. Database Evidence (Amazon DynamoDB)
| File Name | Description | Table Name |
| :--- | :--- | :--- |
| [`dynamodb-employees-table.png`](./dynamodb-employees-table.png) | Master Employee Records Table | `employees` |
| [`dynamodb-salary-components-table.png`](./dynamodb-salary-components-table.png) | Employee Salary Structure & Allowances | `salary_components` |
| [`dynamodb-deductions-table.png`](./dynamodb-deductions-table.png) | Employee Loan, PF %, and TDS Tax Rates | `deductions` |
| [`dynamodb-payroll-runs-table.png`](./dynamodb-payroll-runs-table.png) | Historical Payroll Processing Run Logs | `payroll_runs` |

### 3. Messaging & Event Processing (Amazon SQS)
| File Name | Description | Resource / Queue |
| :--- | :--- | :--- |
| [`sqs-queues-console.png`](./sqs-queues-console.png) | SQS Payroll Queue & Dead-Letter Queue (DLQ) | `automatic-payroll-queue`, `automatic-payroll-dlq` |
| [`sqs-lambda-trigger.png`](./sqs-lambda-trigger.png) | SQS Event Source Mapping Trigger to Worker | `payroll-worker` trigger |

### 4. Serverless Execution & Dependencies (AWS Lambda)
| File Name | Description | Resource |
| :--- | :--- | :--- |
| [`lambda-functions-console.png`](./lambda-functions-console.png) | AWS Lambda Functions Console | `payroll-worker` |
| [`lambda-reportlab-layer.png`](./lambda-reportlab-layer.png) | ReportLab PDF Generation Lambda Layer | `payroll-reportlab-layer` |
| [`lambda-worker-code-structure.png`](./lambda-worker-code-structure.png) | Lambda Source Code & Modular Function Structure | `handler.py`, `payslip_service.py` |
| [`lambda-environment-variables.png`](./lambda-environment-variables.png) | Encrypted Environment Variables (SES Sender) | `SES_SENDER_EMAIL` |

### 5. Storage, Email & Artifact Delivery (S3, SES, PDF)
| File Name | Description | Output Details |
| :--- | :--- | :--- |
| [`generated-payslip-pdf.png`](./generated-payslip-pdf.png) | Official Rendered Payslip PDF Sample | Employee `EMP004` (August 2026) |
| [`s3-payslip-storage.png`](./s3-payslip-storage.png) | Private S3 Bucket Payslip Object Storage | `automatic-payroll-payslips-2026` |
| [`ses-payslip-email.png`](./ses-payslip-email.png) | Amazon SES HTML Email Notification with Download Link | Recipient Employee Inbox |

### 6. Security & Operational Observability (IAM & CloudWatch)
| File Name | Description | Service / Role |
| :--- | :--- | :--- |
| [`iam-payroll-execution-role.png`](./iam-payroll-execution-role.png) | Least-Privilege IAM Worker Execution Role Policies | `PayrollWorkerExecutionRole` |
| [`cloudwatch-execution-log.png`](./cloudwatch-execution-log.png) | CloudWatch Execution Log Streams & Tracing | `/aws/lambda/payroll-worker` |

### 7. HR Management Portal (S3 Static Web Hosting)
| File Name | Description | UI View |
| :--- | :--- | :--- |
| [`hr-portal-dashboard.png`](./hr-portal-dashboard.png) | HR Portal Main Dashboard Overview | Run Payroll & Summary KPI Cards |
| [`hr-portal-system-health.png`](./hr-portal-system-health.png) | System Health & Async Queue Worker Monitor | Gateway, SQS Queue, & Worker Status |
| [`hr-portal-employee-payslips.png`](./hr-portal-employee-payslips.png) | Employee Historical Payslip Search & Ledger | Employee Search & Historical Ledger |
| [`hr-portal-payroll-results.png`](./hr-portal-payroll-results.png) | Execution Results & Gross/Net Pay Breakdown | Detailed Payroll Run Breakdown |
| [`hr-portal-payroll-history.png`](./hr-portal-payroll-history.png) | Historical Payroll Batch Run List | Historical Batch Log |

---

*Extracted and organized automatically for the AWS Automatic Payroll Processing Engine repository.*
