---
title: Interfaccia ICorDebugObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue
helpviewer_keywords:
- ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 937de6a0-6fbf-4ddc-80ea-a6217b73e62b
topic_type:
- apiref
ms.openlocfilehash: e104f8c522af2ee4cd42332b7459f4a2fd185511
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792692"
---
# <a name="icordebugobjectvalue-interface"></a>Interfaccia ICorDebugObjectValue

Sottoclasse di "ICorDebugValue" che rappresenta un valore che contiene un oggetto.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetClass](icordebugobjectvalue-getclass-method.md)|Ottiene un puntatore a interfaccia per la <xref:System.Type> di Common Language Runtime (CLR) dell'oggetto a cui fa riferimento questo `ICorDebugObjectValue`.|  
|[Metodo GetContext](icordebugobjectvalue-getcontext-method.md)|Non implementato.|  
|[Metodo GetFieldValue](icordebugobjectvalue-getfieldvalue-method.md)|Ottiene un puntatore a interfaccia a un [ICorDebugValue](icordebugvalue-interface.md) che rappresenta il valore del campo specificato della classe specificata.|  
|[Metodo GetManagedCopy](icordebugobjectvalue-getmanagedcopy-method.md)|Obsoleta. Non chiamare questo metodo.|  
|[Metodo GetVirtualMethod](icordebugobjectvalue-getvirtualmethod-method.md)|Non implementato.|  
|[Metodo IsValueClass](icordebugobjectvalue-isvalueclass-method.md)|Ottiene un valore che indica se l'oggetto a cui fa riferimento questo `ICorDebugObjectValue` è un tipo di valore.|  
|[Metodo SetFromManagedCopy](icordebugobjectvalue-setfrommanagedcopy-method.md)|Obsoleta. Non chiamare questo metodo.|  
  
## <a name="remarks"></a>Note  
 Un `ICorDebugObjectValue` rimane valido finché il processo di cui è in corso il debug non viene continuato.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
