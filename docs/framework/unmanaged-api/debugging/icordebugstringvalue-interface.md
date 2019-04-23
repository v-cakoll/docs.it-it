---
title: Interfaccia ICorDebugStringValue
ms.date: 03/30/2017
api_name:
- ICorDebugStringValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStringValue
helpviewer_keywords:
- ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: bf84d0af-53e1-4c04-bc5b-7e5f81ba2cc2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6709b14ce8e7bc131f9feb7a277fb41851ee4352
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173992"
---
# <a name="icordebugstringvalue-interface"></a>Interfaccia ICorDebugStringValue
Sottoclasse di ICorDebugHeapValue che viene applicata ai valori di stringa.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetLength](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getlength-method.md)|Ottiene il numero di caratteri nella stringa di cui fa riferimento questo `ICorDebugStringValue`.|  
|[Metodo GetString](../../../../docs/framework/unmanaged-api/debugging/icordebugstringvalue-getstring-method.md)|Ottiene la stringa fa riferimento questo `ICorDebugStringValue`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
