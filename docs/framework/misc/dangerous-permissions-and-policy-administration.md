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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ae24cdcb97e30da0bd4aec6569ef3dcda11488c6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61775765"
---
# <a name="dangerous-permissions-and-policy-administration"></a>Autorizzazioni pericolose e amministrazione dei criteri
Diverse operazioni protette per le quali .NET Framework fornisce le autorizzazioni possono potenzialmente consentire l'elusione del sistema di sicurezza. Queste autorizzazioni pericolose devono essere fornite solo a codice attendibile e solo se necessario. Non esiste in genere alcuna difesa contro malware se viene concesso questo tipo di autorizzazioni.  
  
> [!NOTE]
>  In [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]sono state apportate importanti modifiche al modello di sicurezza e alla terminologia di .NET Framework. Per altre informazioni su queste modifiche, vedere [modifiche della sicurezza](../../../docs/framework/security/security-changes.md).  
  
 Le autorizzazioni pericolose sono illustrate nella tabella seguente.  
  
|Autorizzazioni|Potenziale rischio|  
|----------------|--------------------|  
|<xref:System.Security.Permissions.SecurityPermission>||  
|<xref:System.Security.Permissions.SecurityPermissionFlag.UnmanagedCode>|Consente al codice gestito di chiamare codice non gestito, che molto spesso è pericoloso.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SkipVerification>|Senza verifica il codice può eseguire qualsiasi operazione.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlEvidence>|Una prova non convalidata può eludere i criteri di sicurezza.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPolicy>|La capacità di modificare i criteri di sicurezza può disattivare la protezione.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.SerializationFormatter>|L'uso della serializzazione può eludere i meccanismi di accessibilità. Per informazioni dettagliate, vedere [Sicurezza e serializzazione](../../../docs/framework/misc/security-and-serialization.md).|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlPrincipal>|La capacità di impostare l'entità corrente può eludere la sicurezza basata sui ruoli.|  
|<xref:System.Security.Permissions.SecurityPermissionFlag.ControlThread>|La modifica dei thread è pericolosa a causa dello stato di sicurezza associato ai thread.|  
|<xref:System.Security.Permissions.ReflectionPermission>||  
|<xref:System.MemberAccessException>|Può usare i membri privati per aggirare i meccanismi di accessibilità.|  
  
## <a name="see-also"></a>Vedere anche

- [Linee guida per la generazione di codice sicuro](../../../docs/standard/security/secure-coding-guidelines.md)
