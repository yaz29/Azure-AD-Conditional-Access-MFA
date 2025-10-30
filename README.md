# Azure AD – Conditional Access & MFA

## 🎯 Objetivo
Implementar controles básicos de seguridad en Azure AD (Entra ID):
- Creación de usuarios y roles.
- Habilitar **MFA** (Multi-Factor Authentication).
- Configurar **políticas de acceso condicional**.

## 🛠 What I Built
- Created Microsoft Entra ID users (Alice and Bob) and a dedicated security group MFA-Required-Users.
- Configured a Conditional Access Policy requiring MFA for all sign-ins from that group.
- Applied Zero Trust–aligned identity protection by enforcing contextual access.
- Tested the full flow: login prompt → MFA challenge → access granted only after successful verification.
- Documented all steps, added screenshots, and included an architecture diagram for clarity and recruiter review.

- ## 🛠 Diagram
<img width="1024" height="1536" alt="ChatGPT Image Oct 30, 2025 at 07_35_52 PM" src="https://github.com/user-attachments/assets/11a662b5-87e5-42f5-9a4b-49928c27009f" />

## Conditional Access Decision Flow
<img width="1536" height="1024" alt="conditional-access" src="https://github.com/user-attachments/assets/c8f94d97-4f55-43db-b718-94ab0d015e4b" />

## 🛠 Herramientas
- Microsoft Azure (Free Trial).
- Azure AD / Entra ID.
- Conditional Access Policies 
- Microsoft Authenticator.

## 🚀 Pasos realizados
1. Creación de tenant gratuito en Azure.
2. Alta de dos usuarios: `admin_user` y `employee_user`.
3. Habilitación de MFA obligatorio para `admin_user`.
4. Configuración de una política de acceso condicional:
   - Bloquear inicios de sesión desde fuera de Europa.
   - Aplicada solo a `admin_user`.
5. Pruebas de login:
   - Login válido con MFA ✅
   - Login bloqueado por ubicación 🚫

## 📸 Evidencias
Capturas en carpeta `screenshots/`.

## 📊 Resultados
- MFA protegido para cuentas privilegiadas.
- Acceso condicional bloqueó accesos no autorizados.
— Providing a practical foundation for enterprise-level Identity & Access Management (IAM).

## 🔮 Próximos pasos
- Implementar **Privileged Identity Management (PIM)**.
- Integrar con SIEM (Microsoft Sentinel).
