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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da5c5a12df5689f113857045ba4bcda696bda8f5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756723"
---
# <a name="icordebugheapvalue2createhandle-method"></a>Metodo ICorDebugHeapValue2::CreateHandle
Crea un handle del tipo specificato per il valore di heap rappresentato da questo oggetto ICorDebugHeapValue2.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT CreateHandle (  
    [in] CorDebugHandleType      type,   
    [out] ICorDebugHandleValue   **ppHandle  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `type`  
 [in] Valore dell'enumerazione CorDebugHandleType che specifica il tipo di handle da creare.  
  
 `ppHandle`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugHandleValue che rappresenta il nuovo handle per questo valore di heap.  
  
## <a name="remarks"></a>Note  
 L'handle verrà creato nel dominio dell'applicazione che viene associato il valore di heap e non sarà più valida se il dominio dell'applicazione viene scaricato.  
  
 Più chiamate a questa funzione per lo stesso valore di heap creerà più handle. Poiché gli handle di influire sulle prestazioni del garbage collector, il debugger deve limitarsi a un numero relativamente ridotto di handle (circa 256) che sono attive contemporaneamente.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
