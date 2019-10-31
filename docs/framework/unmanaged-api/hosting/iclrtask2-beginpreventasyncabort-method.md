---
title: Metodo ICLRTask2::BeginPreventAsyncAbort
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: 67841bbcd796e41b3b81f922020fe6c3677730c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124558"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>Metodo ICLRTask2::BeginPreventAsyncAbort
Ritarda la creazione di nuove richieste di interruzione del thread dal risultato di interruzioni di thread sul thread corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|HOST_E_INVALIDOPERATION|Il metodo è stato chiamato su un thread che non è il thread corrente.|  
  
## <a name="remarks"></a>Note  
 La chiamata a questo metodo consente di incrementare di uno il contatore Delay-thread-Abort per il thread corrente.  
  
 Le chiamate a `BeginPreventAsyncAbort` e [ICLRTask2:: EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) possono essere nidificate. Fino a quando il contatore è maggiore di zero, le interruzioni dei thread per il thread corrente vengono posticipate. Se questa chiamata non è associata a una chiamata al metodo `EndPreventAsyncAbort`, è possibile raggiungere uno stato in cui non è possibile recapitare le interruzioni di thread al thread corrente.  
  
 Il ritardo non viene rispettato per un thread che si interrompe automaticamente.  
  
 La funzionalità esposta da questa funzionalità viene usata internamente dalla macchina virtuale (VM). Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale. Ad esempio, la chiamata di `EndPreventAsyncAbort` senza chiamare prima `BeginPreventAsyncAbort` può impostare il contatore su zero quando la VM lo ha incrementato in precedenza. Analogamente, il contatore interno non viene controllato per l'overflow. Se supera il limite integrale perché viene incrementato sia dall'host che dalla macchina virtuale, il comportamento risultante non è specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MSCorEE. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [Interfaccia ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
