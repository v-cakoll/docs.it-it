---
title: Metodo ICLRTask2::EndPreventAsyncAbort
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b18f6b8f6768c0a2980489cf8b84e16a9dd31350
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2endpreventasyncabort-method"></a>Metodo ICLRTask2::EndPreventAsyncAbort
Consente di nuovo o richieste di interruzione del thread restituiscono di thread in sospeso interrompe il thread corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|HOST_E_INVALIDOPERATION|Il metodo è stato chiamato su un thread che non è il thread corrente.|  
  
## <a name="remarks"></a>Note  
 Chiamata di questo contatore decrementa il ritardo di interruzione di metodo per il thread corrente da uno.  
  
 Le chiamate a [Iclrtask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) e `EndPreventAsyncAbort` possono essere annidati. Fino a quando il contatore è maggiore di zero, vengono posticipate interruzioni del thread per il thread corrente.  
  
 La funzionalità esposta da questa funzionalità viene utilizzata internamente dalla macchina virtuale (VM). Un utilizzo improprio di questi metodi può causare un comportamento non specificato nella macchina virtuale. Ad esempio, la chiamata `EndPreventAsyncAbort` senza prima chiamare `BeginPreventAsyncAbort` Impossibile impostare il contatore a zero quando la macchina virtuale ha incrementato in precedenza in. Analogamente, il contatore interno non viene verificato per overflow. Se superato questo limite integrale perché aumenta di host e la macchina virtuale, il comportamento risultante è specificato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Mscoree. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [Interfaccia ICLRTask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [Interfaccia ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Interfaccia IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Interfaccia IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfacce di hosting](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
