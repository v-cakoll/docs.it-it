---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: 30679e1f67c6943bf674a6bbd8bf12be090765a8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203509"
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```csharp  
class ServiceSecurityAuditBehavior : Behavior  
{  
  string AuditLogLocation;  
  string MessageAuthenticationAuditLevel;  
  string ServiceAuthorizationAuditLevel;  
  boolean SuppressAuditFailure;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceSecurityAuditBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceSecurityAuditBehavior dispone delle proprietà seguenti:  
  
### <a name="auditloglocation"></a>AuditLogLocation  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Percorso del registro di controllo.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Tipo di livello di autenticazione dei messaggi utilizzato per registrare eventi di controllo.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Tipi di eventi di autorizzazione registrati nel registro di controllo.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel registro di controllo.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
