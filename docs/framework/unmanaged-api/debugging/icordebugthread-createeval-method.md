---
title: Metodo ICorDebugThread::CreateEval
ms.date: 03/30/2017
api_name:
- ICorDebugThread.CreateEval
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::CreateEval
helpviewer_keywords:
- CreateEval method [.NET Framework debugging]
- ICorDebugThread::CreateEval method [.NET Framework debugging]
ms.assetid: 36605067-33d3-4579-9c72-fb0e551ab0f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2016795e7b2c0588e2bd69e764fb96f7f90b24d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994071"
---
# <a name="icordebugthreadcreateeval-method"></a>Metodo ICorDebugThread::CreateEval
Crea un oggetto ICorDebugEval che raccoglie ed espone la funzionalità di ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEval`  
 [out] Un puntatore all'indirizzo di un `ICorDebugEval` oggetto raccoglie ed espone la funzionalità di questo thread.  
  
## <a name="remarks"></a>Note  
 L'oggetto valutazione effettuerà il push una catena di nuovo nel thread prima di eseguire il calcolo. In questo modo si interromperà il calcolo viene eseguito sul thread fino al completamento della versione di valutazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
