---
title: Interfaccia IHostSecurityManager
ms.date: 03/30/2017
api_name:
- IHostSecurityManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager
helpviewer_keywords:
- IHostSecurityManager interface [.NET Framework hosting]
ms.assetid: c3be2cbd-2d93-438b-9888-9a0251b63c03
topic_type:
- apiref
ms.openlocfilehash: b2c334c7a757c2f4044d08787bdae93ffc2804e4
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803888"
---
# <a name="ihostsecuritymanager-interface"></a>Interfaccia IHostSecurityManager
Fornisce metodi che consentono l'accesso e il controllo sul contesto di sicurezza del thread attualmente in esecuzione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md)|Ottiene l'oggetto [IHostSecurityContext](ihostsecuritycontext-interface.md) richiesto dall'host.|  
|[Metodo ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md)|Richiede che il codice venga eseguito utilizzando le credenziali dell'identità utente corrente.|  
|[Metodo OpenThreadToken](ihostsecuritymanager-openthreadtoken-method.md)|Apre il token di accesso discrezionale associato al thread corrente.|  
|[Metodo RevertToSelf](ihostsecuritymanager-reverttoself-method.md)|Termina la rappresentazione dell'identità dell'utente corrente e restituisce il token del thread originale.|  
|[Metodo SetSecurityContext](ihostsecuritymanager-setsecuritycontext-method.md)|Imposta il contesto di sicurezza per il thread attualmente in esecuzione.|  
|[Metodo SetThreadToken](ihostsecuritymanager-setthreadtoken-method.md)|Imposta un handle per il thread attualmente in esecuzione.|  
  
## <a name="remarks"></a>Osservazioni  
 Un host è in grado di controllare l'accesso al codice a token di thread sia dal Common Language Runtime (CLR) sia dal codice utente. Può inoltre garantire che le informazioni complete sul contesto di sicurezza vengano passate tra le operazioni asincrone o i punti di codice con accesso limitato al codice. `IHostSecurityContext`incapsula queste informazioni sul contesto di sicurezza, che è opaco per CLR.  
  
 CLR gestisce internamente il contesto del thread gestito. Viene eseguita una query sul processo specifico `IHostSecurityManager` nelle situazioni seguenti:  
  
- Nel thread del finalizzatore, durante l'esecuzione del finalizzatore.  
  
- Durante l'esecuzione del costruttore della classe e del modulo.  
  
- In corrispondenza di punti asincroni nel thread di lavoro, in chiamate al metodo [IHostThreadPoolManager:: QueueUserWorkItem](ihostthreadpoolmanager-queueuserworkitem-method.md) .  
  
- In manutenzione delle porte di completamento I/O.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IHostSecurityContext](ihostsecuritycontext-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
