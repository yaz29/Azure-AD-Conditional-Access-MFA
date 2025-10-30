# Azure AD – Conditional Access & MFA

## 🧩 Overview
This lab demonstrates how to protect cloud identities in Microsoft Azure using Conditional Access and Multi-Factor Authentication (MFA).  
The configuration ensures that only authorized users belonging to a specific security group can access cloud resources, and only after successfully completing MFA verification.  

This setup reflects a real-world implementation of Zero Trust security, enforcing identity-based access control to defend against credential compromise and unauthorized access.  

## ⚠️ Real-World Risk
Most cloud breaches originate from compromised user credentials. Attackers use techniques such as phishing, credential stuffing, and brute-force attacks to gain access to sensitive environments.  
Without strong authentication and contextual access controls, even a single leaked password can provide entry to critical systems or confidential data.  

By enforcing Conditional Access with MFA in Azure, organizations significantly reduce the risk of:  
- Unauthorized account access  
- Credential theft  
- Privilege escalation and lateral movement  

This approach aligns with Zero Trust principles verifying every access attempt before granting permissions.  

## 🛠 What I Built
- Created Microsoft Entra ID users (Jasmine & Aaron) and a dedicated security group `MFA-Required-Users`.  
- Configured a Conditional Access Policy requiring MFA for all sign-ins from that group.  
- Applied  Zero Trust–aligned identity protection by enforcing contextual access.  
- Tested the full flow: login prompt → MFA challenge → access granted only after successful verification.  
- Documented all steps, added screenshots, and included an architecture diagram for clarity and recruiter review.  

- ## 🛠 Diagram
<img width="1024" height="1536" alt="ChatGPT Image Oct 30, 2025 at 07_35_52 PM" src="https://github.com/user-attachments/assets/11a662b5-87e5-42f5-9a4b-49928c27009f" />

## 🛠  Conditional Access Decision Flow

<img width="1536" height="1024" alt="conditional_2" src="https://github.com/user-attachments/assets/c2d44f45-bc23-4a0b-9932-7180cf8ee167" />

## ⚙️ Steps Performed  

### 1️⃣ Microsoft Entra ID User Creation  
Created two cloud-only test users in Azure AD for the lab environment:  
- `Jasmine Demo`  
- `Aaron Demo`  
📸 Screenshot: `Users.png`

### 2️⃣ Security Group Setup  
- Created a security group named MFA-Required-Users in Microsoft Entra ID.  
- Added Jasmine & Aaron as members of this group to target MFA enforcement.  
📸 Screenshot: `group-members.png`


### 3️⃣ Per-User MFA Enablement (Legacy)  
- Enabled per-user MFA for both users via the classic MFA settings in Microsoft Entra ID.  
- Verified the MFA status for each account.  
📸 Screenshot: `Per-User-MFA.png`


### 4️⃣ Conditional Access Policy Configuration  
1. Navigated to Microsoft Entra ID → Security → Conditional Access.  
2. Created a policy named Require MFA for MFA-Required-Users.  
3. Assigned the policy to the `MFA-Required-Users` group.  
4. Targeted All Cloud Apps.  
5. Set the access control to Require multi-factor authentication.  
6. Disabled Security Defaults to avoid conflicts.  
7. Enabled the new policy and confirmed it was active.  
📸 Screenshot: `Conditional-Access-Policy.png`

### 5️⃣ MFA Prompt Verification  
- Signed in as Jasmine to test policy enforcement.  
- Verified that an MFA registration prompt appeared before access to resources was granted.  
- Confirmed that the Conditional Access policy was actively enforcing MFA for group members.  
📸 Screenshot: `MFA-prompt.png`


### 6️⃣ Cleanup  
To leave the environment clean and secure:  
- Deleted test users Jasmine & Aaron.  
- Removed the MFA-Required-Users group.  
- Deleted the Conditional Access policy.  
- Disabled per-user MFA settings (if enabled).  
- Verified that no lab-related objects remained in Microsoft Entra ID or Conditional Access.  

## ✅ Tools Result: 

MFA was successfully enforced via Conditional Access for all targeted users, validating the Zero Trust model implementation. 

## 🧰 Tools & Services Used
- Microsoft Azure Portal  
- Microsoft Entra ID (Azure AD)  
- Conditional Access Policies  
- Microsoft Authenticator App  


## 💡 Outcome
By implementing Azure AD Conditional Access with MFA, this lab demonstrates how to strengthen identity protection, enforce secure authentication, and reduce credential-based attack surfaces — providing a practical foundation for enterprise-level Identity & Access Management (IAM).  

