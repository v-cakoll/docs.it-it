---
title: Interfaccia ICorDebugGenericValue
ms.date: 03/30/2017
api_name:
- ICorDebugGenericValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGenericValue
helpviewer_keywords:
- ICorDebugGenericValue interface [.NET Framework debugging]
ms.assetid: bc14f408-b359-4c8c-ade2-888ccdf7261b
topic_type:
- apiref
ms.openlocfilehash: 312b8b005998da44feb5ae24ab4a0a17bb948a3f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138566"
---
# <a name="icordebuggenericvalue-interface"></a>Interfaccia ICorDebugGenericValue

Sottoclasse di "ICorDebugValue" che si applica a tutti i valori. Questa interfaccia fornisce i metodi Get e Set per il valore.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-getvalue-method.md)|Copia il valore nel buffer specificato.|  
|[Metodo SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebuggenericvalue-setvalue-method.md)|Copia un nuovo valore dal buffer specificato.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugGenericValue` è un'interfaccia secondaria perché non utilizzabile in remoto.  
  
 Per i tipi di riferimento, il valore è il riferimento anziché il contenuto del riferimento.  
  
 Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
