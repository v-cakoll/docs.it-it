---
title: ServiceAuthorizationBehavior
ms.date: 03/30/2017
ms.assetid: 77dad8e8-fea4-4d1c-b366-2f01a2a87f78
ms.openlocfilehash: 51555e3357b8c33a53261c4894d97798b0a05656
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/22/2019
ms.locfileid: "59972836"
---
# <a name="serviceauthorizationbehavior"></a>ServiceAuthorizationBehavior
ServiceAuthorizationBehavior  
  
## <a name="syntax"></a>Sintassi  
  
```csharp
class ServiceAuthorizationBehavior : Behavior  
{  
  boolean ImpersonateCallerForAllOperations;  
  string PrincipalPermissionMode;  
  string RoleProvider;  
  string ServiceAuthorizationManager;  
};  
```  
  
## <a name="methods"></a>Metodi  
 La classe ServiceAuthorizationBehavior non definisce metodi.  
  
## <a name="properties"></a>Proprietà  
 La classe ServiceAuthorizationBehavior dispone delle proprietà seguenti:  
  
### <a name="impersonatecallerforalloperations"></a>ImpersonateCallerForAllOperations  
 Tipo di dati: booleano  
  
 Tipo di accesso: Sola lettura  
  
 Valore che controlla se il servizio tenta di eseguire una rappresentazione utilizzando le credenziali fornite dal messaggio in ingresso.  
  
### <a name="principalpermissionmode"></a>PrincipalPermissionMode  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Entità di protezione utilizzata per eseguire operazioni nel server.  
  
### <a name="roleprovider"></a>RoleProvider  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Nome del provider del ruolo ASP.NET.  
  
### <a name="serviceauthorizationmanager"></a>ServiceAuthorizationManager  
 Tipo di dati: stringa  
  
 Tipo di accesso: Sola lettura  
  
 Gestore autorizzazioni utilizzato per l'autorizzazione personalizzata.  
  
## <a name="requirements"></a>Requisiti  
  
|MOF|Dichiarato in Servicemodel.mof.|  
|---------|-----------------------------------|  
|Spazio dei nomi|Definito in root\ServiceModel|  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>
