---
title: Metodo ICorDebugProcess::ClearCurrentException
ms.date: 03/30/2017
api_name:
- ICorDebugProcess.ClearCurrentException
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess::ClearCurrentException
helpviewer_keywords:
- ClearCurrentException method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::ClearCurrentException method [.NET Framework debugging]
ms.assetid: 9e02ee1a-e495-4578-bfb5-b946274bede7
topic_type:
- apiref
ms.openlocfilehash: b8d20de990ff4a27a82590342494a307c986457e
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207400"
---
# <a name="icordebugprocessclearcurrentexception-method"></a>Metodo ICorDebugProcess::ClearCurrentException
Cancella l'eccezione non gestita corrente sul thread specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ClearCurrentException([in] DWORD threadID);  
```  
  
## <a name="parameters"></a>Parametri  
 `threadID`  
 in ID del thread in cui verrà cancellata l'eccezione non gestita corrente.  
  
## <a name="remarks"></a>Osservazioni  
 Chiamare questo metodo prima di chiamare [ICorDebugController:: continue](icordebugcontroller-continue-method.md) quando un thread ha segnalato un'eccezione non gestita che deve essere ignorata dall'oggetto del debug. Questa operazione eliminerà gli eventi in banda (IB) e fuori banda (OOB) in attesa sul thread specificato. Tutti i punti di interruzione OOB e le eccezioni a singolo passaggio vengono cancellati automaticamente.  
  
 Usare [ICorDebugThread2:: InterceptCurrentException](icordebugthread2-interceptcurrentexception-method.md) per intercettare l'eccezione gestita corrente su un thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
