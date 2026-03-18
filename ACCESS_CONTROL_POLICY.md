# Access Control Policy

**CHOAM Technologies**  
**Effective Date:** January 1, 2026  
**Last Reviewed:** March 17, 2026  
**Document Owner:** Security Team

---

## 1. Purpose

This policy establishes requirements for controlling access to CHOAM production systems, infrastructure, and sensitive data. It ensures that access is granted based on business need, follows the principle of least privilege, and is regularly reviewed.

## 2. Scope

This policy applies to:
- All employees, contractors, and third parties with access to CHOAM systems
- All production infrastructure and environments
- All systems containing sensitive data (customer data, credentials, cryptographic material)

## 3. Access Control Principles

### 3.1 Least Privilege
Access rights are granted based on the minimum permissions necessary to perform job functions. Elevated privileges require documented justification and additional approval.

### 3.2 Separation of Duties
Critical functions are divided among multiple individuals to prevent unauthorized actions. No single individual has complete control over sensitive operations.

### 3.3 Need-to-Know
Access to sensitive data is restricted to individuals who require it for legitimate business purposes.

## 4. Role-Based Access Control (RBAC)

### 4.1 Role Definitions
Access is managed through predefined roles aligned with job functions:

| Role | Description | Access Level |
|------|-------------|--------------|
| Administrator | System and infrastructure management | Full administrative access |
| Developer | Application development and deployment | Development and staging environments |
| Operator | Production monitoring and incident response | Read access to production, limited write |
| Auditor | Compliance and security review | Read-only access to logs and configurations |

### 4.2 Role Assignment
- Roles are assigned based on job function and documented in the access management system
- Role changes require manager approval and are logged
- Users may hold multiple roles where business need is demonstrated

## 5. Authentication Requirements

### 5.1 Human Users
- Multi-factor authentication (MFA) is required for all production access
- Passwords must meet complexity requirements (minimum 16 characters, mixed case, numbers, symbols)
- Session timeouts enforce re-authentication after periods of inactivity

### 5.2 Non-Human Identities
- Service accounts use OAuth tokens or mTLS certificates
- API keys are scoped to minimum required permissions
- Credentials are rotated according to the credential management schedule
- Secrets are stored in approved secrets management systems (not in code or configuration files)

## 6. Access Provisioning and De-provisioning

### 6.1 Provisioning
1. Access requests are submitted through the ticketing system
2. Requests require manager approval
3. Security team reviews requests for compliance with this policy
4. Access is granted and logged in the access management system

### 6.2 Modification
- Role changes follow the same approval workflow as new access
- Temporary elevated access expires automatically after the approved duration

### 6.3 De-provisioning
- Access is revoked within 24 hours of employment termination
- Access is modified within 48 hours of role transfer
- Automated systems monitor HR events and trigger de-provisioning workflows
- Terminated user credentials are invalidated across all systems

## 7. Access Reviews

### 7.1 Periodic Reviews
- User access is reviewed quarterly by system owners
- Privileged access is reviewed monthly
- Service account access is reviewed quarterly

### 7.2 Review Process
1. System owners receive access reports
2. Each access grant is validated against current business need
3. Unnecessary access is revoked
4. Review completion is documented and retained

## 8. Logging and Monitoring

### 8.1 Access Logging
All access events are logged, including:
- Authentication attempts (successful and failed)
- Authorization decisions
- Privilege escalation
- Administrative actions

### 8.2 Monitoring
- Automated alerts for anomalous access patterns
- Failed authentication attempts trigger account lockout after 5 attempts
- Security team reviews access logs weekly

## 9. Third-Party Access

- Third-party access requires a signed agreement and security assessment
- Access is limited to specific systems and time periods
- Third-party activity is logged and monitored
- Access is reviewed and revoked when no longer needed

## 10. Exceptions

Exceptions to this policy require:
- Written justification documenting business need
- Risk assessment
- Approval from the Security Team
- Time-bound duration with automatic expiration
- Documentation retained for audit purposes

## 11. Enforcement

Violations of this policy may result in:
- Immediate access revocation
- Disciplinary action
- Termination of employment or contract

## 12. Review and Updates

This policy is reviewed annually and updated as needed to address:
- Changes in business operations
- New security threats
- Regulatory requirements
- Audit findings

---

**Document Control**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-01-01 | Security Team | Initial policy |
| 1.1 | 2026-03-17 | Security Team | Annual review, no changes |
