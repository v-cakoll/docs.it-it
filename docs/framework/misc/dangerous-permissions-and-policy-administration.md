---
title: Autorizzazioni pericolose e amministrazione dei criteri
ms.date: 03/30/2017
helpviewer_keywords:
- permissions [.NET Framework], policy administration
- security [.NET Framework], dangerous permissions
- code security, dangerous permissions
- secure coding, dangerous permissions
- permissions [.NET Framework], dangerous
ms.assetid: 1929e854-23a0-4bb1-94be-e8aa3b609e32
ms.openlocfilehash: 15d28ff7d11b5d15ce44d9ab1f56548256850ff8
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645752"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Autorizzazioni pericolose e amministrazione dei criteri
Diverse operazioni protette per le quali .NET Framework fornisce le autorizzazioni possono potenzialmente consentire l'elusione del sistema di sicurezza. Queste autorizzazioni pericolose devono essere fornite solo a codice attendibile e solo se necessario. Non esiste in genere alcuna difesa contro malware se viene concesso questo tipo di autorizzazioni.  
  
> [!NOTE]
> In .NET Framework 4 sono state apportate importanti modifiche al modello di sicurezza e alla terminologia di .NET Framework. Per ulteriori informazioni su queste modifiche, vedere [Modifiche alla sicurezza](https://docs.microsoft.com/previous-versions/dotnet/framework/security/security-changes).  
  
 Le autorizzazioni pericolose sono illustrate nella tabella seguente.  
  
|Autorizzazione|Potenziale rischio|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Consente al codice gestito di chiamare codice non gestito, che molto spesso è pericoloso.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Senza verifica il codice può eseguire qualsiasi operazione.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|Una prova non convalidata può eludere i criteri di sicurezza.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|La capacità di modificare i criteri di sicurezza può disattivare la protezione.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|L'uso della serializzazione può eludere i meccanismi di accessibilità. Per informazioni dettagliate, vedere [Sicurezza e serializzazione](security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|La capacità di impostare l'entità corrente può eludere la sicurezza basata sui ruoli.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|La modifica dei thread è pericolosa a causa dello stato di sicurezza associato ai thread.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Può usare i membri privati per aggirare i meccanismi di accessibilità.|  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../standard/security/secure-coding-guidelines.md)
