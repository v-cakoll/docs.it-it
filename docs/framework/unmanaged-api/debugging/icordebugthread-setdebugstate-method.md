---
title: Metodo ICorDebugThread::SetDebugState
ms.date: 03/30/2017
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
ms.openlocfilehash: 05ae2791ee7f8bd31be38ec4d2117ddc3c2ea2bc
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83377938"
---
# <a name="icordebugthreadsetdebugstate-method"></a>Metodo ICorDebugThread::SetDebugState
Imposta i flag che descrivono lo stato di debug di ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `state`  
 in Combinazione bit per bit di valori di enumerazione CorDebugThreadState che specificano lo stato di debug di questo thread.  
  
## <a name="remarks"></a>Osservazioni  
 `SetDebugState`imposta lo stato di debug corrente del thread. (Lo stato di debug corrente) rappresenta lo stato di debug se il processo deve essere continuato, non lo stato corrente effettivo. Il valore normale per questo è THREAD_RUN. Solo il debugger può influire sullo stato di debug di un thread. Gli Stati di debug durano per ultimi, quindi se si vuole tenere un thread THREAD_SUSPENDed su più prosegue, è possibile impostarlo una volta e successivamente non doverlo preoccupare. La sospensione dei thread e la ripresa del processo possono causare deadlock, anche se in genere è improbabile. Si tratta di una qualità intrinseca di thread e processi ed è basata sulla progettazione. Un debugger può interrompere e riprendere i thread in modo asincrono per interrompere il deadlock. Se lo stato utente del thread include USER_UNSAFE_POINT, il thread può bloccare una Garbage Collection (GC). Ciò significa che il thread sospeso ha un'opportunità molto più elevata di causare un deadlock. Questo potrebbe non influire sugli eventi di debug già accodati. Un debugger dovrebbe quindi svuotare l'intera coda degli eventi (chiamando [ICorDebugController:: HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)) prima di sospendere o riprendere i thread. In caso contrario, può ottenere eventi in un thread che ritiene che sia già sospeso.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
