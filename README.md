# Elephant-Datart-
‌Vulnerability Title：Elephant Datart Information Disclosure Vulnerability

Vendor Name：Elephant Datart

Product Name：Elephant Datart

Affected Versions：1.0.0-rc3

Official website：https://github.com/running-elephant/datart

Vulnerability Type: Sensitive Information Leakage / Weak Encryption Configuration

Repetition：
version 1.0.0-rc3
<img width="1421" height="918" alt="1" src="https://github.com/user-attachments/assets/844e63b7-3f80-43a4-a5f3-4b7cb901faf2" />

Log in with a regular account, access the data source list, and the system prompts 'You do not have permission to access this page'.

<img width="1563" height="636" alt="2" src="https://github.com/user-attachments/assets/56b483a6-d9c2-4f96-823e-e51e9e19bc16" />

The packet capture detects the presence of a plaintext account, server address, and encryption password in the response value.

<img width="1971" height="701" alt="3" src="https://github.com/user-attachments/assets/b031e66d-dc00-4cbc-a57c-7293b5da97df" />

Through the CMS open source project, find the source code:
found AESutils
<img width="1488" height="1041" alt="4" src="https://github.com/user-attachments/assets/b2a58f8d-211a-4294-b521-237576a6a6b3" />
track getTokensecret method，Discover the hardcoded key。
<img width="1485" height="810" alt="5" src="https://github.com/user-attachments/assets/9bc75024-cd23-4254-a618-0508af1d620a" />

Write a decryption script：
<img width="1401" height="1113" alt="6" src="https://github.com/user-attachments/assets/5fc7c850-302a-43e6-b244-475436d88459" />
