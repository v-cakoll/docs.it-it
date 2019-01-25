---
title: Interfaccia ICLRTask2
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cbd627eff9318fce38ec238e5fa686cc9d759b8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627187"
---
# <a name="iclrtask2-interface"></a>Interfaccia ICLRTask2
Fornisce tutte le funzionalità dei [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaccia; inoltre, fornisce metodi che consentono le interruzioni dei thread per essere ritardato sul thread corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Ritardi nuove richieste di interruzione sul thread corrente.|  
|[Metodo EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Consente di nuovo o in sospeso alle richieste di interruzione di thread ottengano in thread viene interrotto nel thread corrente.|  
  
## <a name="remarks"></a>Note  
 Il `ICLRTask2` interfaccia eredita il `ICLRTask` l'interfaccia e aggiunge i metodi che consentono all'host ritardare le interruzioni di thread, per proteggere un'area di codice che non deve avere esito negativo. La chiamata `BeginPreventAsyncAbort` incrementa il contatore di ritardo di interruzione per il thread corrente e chiamare il metodo `EndPreventAsyncAbort` decrementa è. Le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` possono essere annidati. Ritardo fino a quando il contatore è maggiore di zero, interruzioni di thread per il thread corrente.  
  
 Se le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` non sono abbinate, è possibile raggiungere uno stato nel quale thread interruzioni non possono essere recapitate al thread corrente.  
  
 Il ritardo non viene applicato per un thread che interrompe se stesso.  
  
 La funzionalità che viene esposto da questa funzionalità viene utilizzata internamente dalla macchina virtuale (VM). Un uso improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale. Ad esempio, chiamando `EndPreventAsyncAbort` senza prima chiamare `BeginPreventAsyncAbort` è stato possibile impostare il contatore a zero quando la macchina virtuale in precedenza ha incrementato in. Analogamente, il contatore interno non viene controllato dell'overflow. Se l'utilizzo supera il limite di integrale perché aumenta di host e la macchina virtuale, il comportamento risultante è specificato.  
  
 Per informazioni sui membri ereditata dal `ICLRTask` e sugli altri utilizzi di questa interfaccia, vedere la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
