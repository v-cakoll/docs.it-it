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
ms.openlocfilehash: b067ca72e030bce24a7efde5e3488a00024e9613
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762867"
---
# <a name="iclrtask2-interface"></a>Interfaccia ICLRTask2
Fornisce tutte le funzionalità dell'interfaccia [ICLRTask](iclrtask-interface.md) ; fornisce inoltre metodi che consentono interruzioni di thread in ritardo sul thread corrente.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md)|Ritarda le nuove richieste di interruzione del thread sul thread corrente.|  
|[Metodo EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md)|Consente alle richieste di interruzione di thread nuove o in sospeso di generare interruzioni di thread sul thread corrente.|  
  
## <a name="remarks"></a>Osservazioni  
 L' `ICLRTask2` interfaccia eredita l' `ICLRTask` interfaccia e aggiunge metodi che consentono all'host di ritardare le interruzioni dei thread, per proteggere un'area di codice che non deve avere esito negativo. `BeginPreventAsyncAbort`La chiamata a incrementa il contatore Delay-thread-Abort per il thread corrente e la chiamata `EndPreventAsyncAbort` viene decrementata. Le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` possono essere annidate. Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate.  
  
 Se le chiamate a `BeginPreventAsyncAbort` e `EndPreventAsyncAbort` non sono abbinate, è possibile raggiungere uno stato in cui non è possibile recapitare le interruzioni di thread al thread corrente.  
  
 Il ritardo non viene rispettato per un thread che si interrompe automaticamente.  
  
 La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM). Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale. Ad esempio, `EndPreventAsyncAbort` la chiamata a senza prima chiamata `BeginPreventAsyncAbort` potrebbe impostare il contatore su zero quando la macchina virtuale lo ha incrementato in precedenza. Analogamente, il contatore interno non viene controllato per l'overflow. Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.  
  
 Per informazioni sui membri ereditati da `ICLRTask` e sugli altri utilizzi di questa interfaccia, vedere l'interfaccia [ICLRTask](iclrtask-interface.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRTask](iclrtask-interface.md)
- [Interfaccia ICLRTaskManager](iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](ihosttask-interface.md)
- [Interfaccia IHostTaskManager](ihosttaskmanager-interface.md)
- [Interfacce di hosting](hosting-interfaces.md)
