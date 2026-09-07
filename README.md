# Part A
Fraudulent orders in online retailer such as STADIOalot remain a concern as they erode profit margin and undermine customer trust.
Despite continuous investment in developing the site, customer support channels, and fraud prevention measures, vulnerabilities remain that fraudsters exploit 
through phishing, typo squatting, smishing, identity theft, marketplace manipulation, return policy abuse, and chargebacks. 

However, there has been a small but rising stream of fraudulent payments and charge back orders which circumvent existing rule-based systems. 
41,000 products from the vendors vary enormously in quality: customers complain about some of them, some of them sell counterfeit products, 
some of them do not ship their products on time. STADIOalot monitors them and they respond as they happen, as opposed to observing their patterns 
and detecting them early before they occur. 

Addressing this issue is important because STADIOalot’s 2030 strategy is to keep the platform clean through catching fraudulent activity and weeding out 
poor sellers early, as a result protecting margin and customer trust. 

Data Science methods may assist by providing powerful tools to tackle this challenge. Techniques such as anomaly detection, predictive modelling, and 
behavioural analytics can be applied to large transactional datasets to uncover hidden patterns and identify suspicious activity.
Anomaly detection can be used to identify data points, events, or observations that deviate significantly from the usual behaviour or pattern in the dataset. 
These anomalies can show possible errors, fraud, security breaches, or system failures.
Predictive Modelling uses Statistical and Machine Learning algorithms to predict outcomes using historical data. Predictive Modelling can help to predict 
marketplace sellers who are more likely to sell counterfeits or low-quality products.
 
Therefore, this study seeks to generate evidence that may support decision making by using large transactional datasets to uncover hidden patterns and 
identify suspicious activity i.e. Fraudulent activity.

Proof of AI usage:
https://claude.ai/share/0e750b80-9499-415d-8523-cc6d23996840





# Part B
Despite the availability of transactional and marketplace data, fraudulent activity continues to undermine STADIOalot’s profit margins and customer trust. 
Current rule‑based systems, while useful for basic monitoring, fail to anticipate evolving fraud tactics such as phishing, smishing, identity theft, marketplace 
manipulation, and chargebacks. These vulnerabilities create gaps in detection, allowing fraudsters to exploit weaknesses and erode both financial performance and 
customer confidence in the platform.

STADIOalot’s vendor ecosystem further complicates the challenge. With over 41,000 products listed, sellers vary widely in quality. Some deliver counterfeit goods, 
others fail to ship on time, and many generate customer complaints. While STADIOalot monitors these issues, its approach remains reactive, addressing fraud and 
poor vendor practices only after they occur. This reactive stance not only weakens operational resilience but also threatens the company’s long‑term 
sustainability in the competitive online retail sector.

It remains unclear whether transactional datasets, customer demographics, and seller performance histories can be leveraged to uncover hidden fraud patterns that 
reliably indicate suspicious behavior. Traditional systems lack the sophistication to integrate these diverse data sources into proactive detection strategies.

Therefore, this study aims to examine the effectiveness of anomaly detection and predictive modelling techniques applied to STADIOalot’s flagged orders and 
transaction histories. By investigating whether these methods can identify fraudulent activity earlier and more accurately, the study seeks to provide evidence 
that informs decision‑makers, supports STADIOalot’s 2030 strategy of maintaining a clean marketplace, reduces financial losses, and strengthens customer trust.

Proof of AI usage
https://claude.ai/share/fcc906bb-b821-4359-af2f-ead1c7d912ae





# Part E
| RAAID | Description |       
| --- | --- |
| Risks | 1. Poor data quality – STADIOalot's transactional logs may contain missing or inconsistent records, reducing fraud model accuracy.<br>2. Model bias – Fraud detection may unfairly flag certain sellers or customers, damaging STADIOalot's reputation.<br>3. Scalability challenges – As STADIOalot grows, fraud models may struggle to handle millions of transactions efficiently.<br>4. False negatives – Fraudulent orders slipping through could erode customer trust and margins.<br>5. Integration difficulties – Embedding fraud models into STADIOalot's existing e commerce platform may disrupt operations. |
| Actions | 1. Data cleaning – Standardize STADIOalot's order, payment, and seller datasets before analysis.<br>2. Bias testing – Validate models to ensure fair treatment of sellers and customers.<br>3. Continuous monitoring – Retrain fraud models regularly as STADIOalot's transaction volume grows.<br>4. Stakeholder engagement – Work with STADIOalot's fraud analysts, IT, and vendor management teams.<br>5. Pilot deployment – Test fraud models on a subset of STADIOalot's marketplace before full rollout. |
| Assumptions | 1. STADIOalot's transactional and marketplace data will be accessible for analysis.<br>2. Fraudulent activity is present in sufficient volume to train models.<br>3. Anomaly detection and predictive modelling are suitable for STADIOalot's fraud challenges.<br>4. STADIOalot management supports data driven fraud prevention aligned with the 2030 strategy.<br>5. Customers and sellers will continue generating behavioral data that can be leveraged. |
| Issues | 1. Data privacy – Handling STADIOalot's customer demographics must comply with South African data protection laws.<br>2. Vendor resistance – Sellers flagged as high risk may dispute findings, creating operational and reputational challenges. |
| Decisions | 1. Algorithm choice – Decide whether Isolation Forest, Random Forest, or hybrid models best fit STADIOalot's fraud detection needs.<br>2. Implementation strategy – Determine if fraud detection should run in real time during checkout or as batch analysis after transactions. |
| Dependencies | 1. Data availability – Access to STADIOalot's transactional, customer, and marketplace datasets.<br>2. Technical infrastructure – Adequate computing resources to run fraud detection models at scale.<br>3. Management approval – STADIOalot leadership must endorse fraud detection initiatives.<br>4. Regulatory compliance – Adherence to South African financial and data protection regulations.<br>5. Vendor cooperation – Sellers must provide accurate product and delivery information to support fraud analysis. |
