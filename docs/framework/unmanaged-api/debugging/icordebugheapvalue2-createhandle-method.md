---
title: Metodo ICorDebugHeapValue2::CreateHandle
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue2.CreateHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue2::CreateHandle
helpviewer_keywords:
- CreateHandle method [.NET Framework debugging]
- ICorDebugHeapValue2::CreateHandle method [.NET Framework debugging]
ms.assetid: fbc418e8-fa22-420d-84ec-e0e1800db041
topic_type:
- apiref
ms.openlocfilehash: b9eab1274f2d0ad562c0dec6adeddb85c6cfc458
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138387"
---
# <a name="icordebugheapvalue2createhandle-method"></a>Metodo ICorDebugHeapValue2::CreateHandle
Crea un handle del tipo specificato per il valore dell'heap rappresentato da questo oggetto ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `type`  
 in Valore dell'enumerazione CorDebugHandleType che specifica il tipo di handle da creare.  
  
 `ppHandle`  
 out Puntatore all'indirizzo di un oggetto ICorDebugHandleValue che rappresenta il nuovo handle per questo valore dell'heap.  
  
## <a name="remarks"></a>Note  
 L'handle verrà creato nel dominio applicazione associato al valore dell'heap e diventerà non valido se il dominio applicazione viene scaricato.  
  
 Più chiamate a questa funzione per lo stesso valore heap creeranno più handle. Poiché gli handle influiscono sulle prestazioni del Garbage Collector, il debugger deve limitarsi a un numero relativamente piccolo di handle (circa 256) attivi alla volta.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
