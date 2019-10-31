---
title: Metodo ICorDebugHeapValue::IsValid
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue.IsValid
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue::IsValid
helpviewer_keywords:
- IsValid method [.NET Framework debugging]
- ICorDebugHeapValue::IsValid method [.NET Framework debugging]
ms.assetid: 68e20e62-203d-46d8-bb91-8d3c61cfacc3
topic_type:
- apiref
ms.openlocfilehash: 7edf0065fa7eb39dada167a682f2b634a438f1f3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138404"
---
# <a name="icordebugheapvalueisvalid-method"></a>Metodo ICorDebugHeapValue::IsValid
Ottiene un valore che indica se l'oggetto rappresentato da questo ICorDebugHeapValue è valido.  
  
 Questo metodo è stato deprecato nella versione .NET Framework 2,0.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT IsValid (  
    [out] BOOL    *pbValid  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbValid`  
 out Puntatore a un valore booleano che indica se questo valore nell'heap è valido.  
  
## <a name="remarks"></a>Note  
 Il valore non è valido se è stato recuperato dal Garbage Collector.  
  
 Questo metodo è stato deprecato. Nel .NET Framework 2,0, tutti i valori sono validi fino a quando non viene chiamato [ICorDebugController:: continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) , quindi i valori vengono invalidati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
