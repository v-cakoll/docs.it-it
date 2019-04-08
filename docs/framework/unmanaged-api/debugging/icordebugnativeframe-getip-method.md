---
title: Metodo ICorDebugNativeFrame::GetIP
ms.date: 03/30/2017
api_name:
- ICorDebugNativeFrame.GetIP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugNativeFrame::GetIP
helpviewer_keywords:
- GetIP method, ICorDebugNativeFrame interface [.NET Framework debugging]
- ICorDebugNativeFrame::GetIP method [.NET Framework debugging]
ms.assetid: 99f693f3-d3b9-4fd8-9d09-b8efd03f7b67
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38f913b742f7ece2f136454f801ae780124aed87
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59073533"
---
# <a name="icordebugnativeframegetip-method"></a>Metodo ICorDebugNativeFrame::GetIP
Ottiene il codice nativo offset posizione a cui è attualmente impostato il puntatore all'istruzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetIP (  
    [out] ULONG32           *pnOffset  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnOffset`  
 [out] Puntatore alla posizione di offset nel codice nativo.  
  
## <a name="remarks"></a>Note  
 Se lo stack frame che è rappresentato da questo "ICorDebugNativeFrame" è attivo, l'offset è l'indirizzo dell'istruzione successiva da eseguire. Se lo stack frame corrente non è attivo, l'offset è l'indirizzo dell'istruzione successiva da eseguire quando viene riattivato lo stack frame.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
