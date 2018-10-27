---
title: ServiceSecurityAuditBehavior
ms.date: 03/30/2017
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
ms.openlocfilehash: e8b24877c2d76a3f2f90c27ae83374c7bca1328b
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50181160"
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
  
 Tipo di accesso: sola lettura  
  
 Percorso del registro di controllo.  
  
### <a name="messageauthenticationauditlevel"></a>MessageAuthenticationAuditLevel  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Tipo di livello di autenticazione dei messaggi utilizzato per registrare eventi di controllo.  
  
### <a name="serviceauthorizationauditlevel"></a>ServiceAuthorizationAuditLevel  
 Tipo di dati: stringa  
  
 Tipo di accesso: sola lettura  
  
 Tipi di eventi di autorizzazione registrati nel registro di controllo.  
  
### <a name="suppressauditfailure"></a>SuppressAuditFailure  
 Tipo di dati: booleano  
  
 Tipo di accesso: sola lettura  
  
 Valore booleano che specifica il comportamento per l'eliminazione di errori di scrittura nel registro di controllo.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior>
