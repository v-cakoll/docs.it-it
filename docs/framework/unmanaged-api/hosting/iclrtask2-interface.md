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
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124529"
---
# <a name="iclrtask2-interface"></a>Interfaccia ICLRTask2
Fornisce tutte le funzionalità dell'interfaccia [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) ; fornisce inoltre metodi che consentono interruzioni di thread in ritardo sul thread corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Ritarda le nuove richieste di interruzione del thread sul thread corrente.|  
|[Metodo EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Consente alle richieste di interruzione di thread nuove o in sospeso di generare interruzioni di thread sul thread corrente.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICLRTask2` eredita l'interfaccia `ICLRTask` e aggiunge metodi che consentono all'host di ritardare le interruzioni dei thread, per proteggere un'area di codice che non deve avere esito negativo. La chiamata di `BeginPreventAsyncAbort` incrementa il contatore Delay-thread-Abort per il thread corrente e la chiamata `EndPreventAsyncAbort` la decrementa. Le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` possono essere nidificate. Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate.  
  
 Se le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` non sono abbinate, è possibile raggiungere uno stato in cui non è possibile recapitare le interruzioni di thread al thread corrente.  
  
 Il ritardo non viene rispettato per un thread che si interrompe automaticamente.  
  
 La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM). Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale. Ad esempio, la chiamata di `EndPreventAsyncAbort` senza chiamare prima `BeginPreventAsyncAbort` può impostare il contatore su zero quando la VM lo ha incrementato in precedenza. Analogamente, il contatore interno non viene controllato per l'overflow. Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.  
  
 Per informazioni sui membri ereditati da `ICLRTask` e sugli altri utilizzi di questa interfaccia, vedere l'interfaccia [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
