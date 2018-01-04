---
title: ServiceSecurityAuditBehavior
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2c5809e7-5364-44ce-bc71-848be4672e2a
caps.latest.revision: "8"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ea9c04c201ff022fcea54b81a998b7020fb2a836
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="servicesecurityauditbehavior"></a>ServiceSecurityAuditBehavior
ServiceSecurityAuditBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
