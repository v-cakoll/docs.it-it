---
title: Interfaccia IHostSecurityManager
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSecurityManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSecurityManager
helpviewer_keywords: IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2b3d67328dbf68491d319e55e63a9c3540cd1ee4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsecuritymanager-interface"></a>Interfaccia IHostSecurityManager
Fornisce metodi che consentono l'accesso e controllo sul contesto di protezione del thread attualmente in esecuzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetSecurityContext (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Ottiene l'oggetto richiesto [IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md) dall'host.|  
|[ImpersonateLoggedOnUser (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-impersonateloggedonuser-method.md)|Le richieste di codice da eseguire utilizzando le credenziali dell'identità dell'utente corrente.|  
|[OpenThreadToken (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-openthreadtoken-method.md)|Apre il token di accesso discrezionale associato al thread corrente.|  
|[RevertToSelf (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md)|Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token thread originale.|  
|[SetSecurityContext (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md)|Imposta il contesto di sicurezza per il thread attualmente in esecuzione.|  
|[SetThreadToken (metodo)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setthreadtoken-method.md)|Imposta un handle per il thread attualmente in esecuzione.|  
  
## <a name="remarks"></a>Note  
 Un host può controllare l'accesso di codice ai token di thread dal common language runtime (CLR) e codice utente. Può inoltre garantire che la sicurezza completa le informazioni di contesto viene passate attraverso operazioni asincrone o punti di codice con accesso di codice con restrizioni. `IHostSecurityContext`incapsula queste informazioni di contesto di sicurezza, sono opache a CLR.  
  
 Common Language Runtime gestisce il contesto di thread gestiti internamente. Viene eseguita una query specifica del processo `IHostSecurityManager` nelle situazioni seguenti:  
  
-   Nel thread finalizzatore, durante l'esecuzione del finalizzatore.  
  
-   Durante l'esecuzione di costruttore di classe e modulo.  
  
-   In punti asincroni del thread di lavoro, nelle chiamate al [IHostThreadPoolManager:: QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md) metodo.  
  
-   In manutenzione di porte di completamento i/o.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IHostSecurityContext (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
