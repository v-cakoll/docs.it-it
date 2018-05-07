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
ms.openlocfilehash: 5e2d99d85a6e6b09558e5941d08a7f522aaf66cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugthreadcreateeval-method"></a>Metodo ICorDebugThread::CreateEval
Crea un oggetto ICorDebugEval che raccoglie ed espone la funzionalità di ICorDebugThread.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CreateEval (  
    [out] ICorDebugEval   **ppEval  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppEval`  
 [out] Un puntatore all'indirizzo di un `ICorDebugEval` che raccoglie ed espone la funzionalità di questo thread.  
  
## <a name="remarks"></a>Note  
 L'oggetto di valutazione determinerà una nuova catena sul thread prima di effettuare il relativo calcolo. In questo modo si interromperà il calcolo viene eseguito sul thread fino al completamento della valutazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
