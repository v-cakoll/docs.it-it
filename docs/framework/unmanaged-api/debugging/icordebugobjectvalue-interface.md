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
ms.openlocfilehash: 603ab20b57dc4ba736b0342797d0be649a5bebc4
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83207486"
---
# <a name="icordebugobjectvalue-interface"></a>Interfaccia ICorDebugObjectValue

Sottoclasse di "ICorDebugValue" che rappresenta un valore che contiene un oggetto.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetClass](icordebugobjectvalue-getclass-method.md)|Ottiene un puntatore a interfaccia per il Common Language Runtime (CLR) <xref:System.Type> dell'oggetto a cui `ICorDebugObjectValue` fa riferimento.|  
|[Metodo GetContext](icordebugobjectvalue-getcontext-method.md)|Non implementato.|  
|[Metodo GetFieldValue](icordebugobjectvalue-getfieldvalue-method.md)|Ottiene un puntatore a interfaccia a un [ICorDebugValue](icordebugvalue-interface.md) che rappresenta il valore del campo specificato della classe specificata.|  
|[Metodo GetManagedCopy](icordebugobjectvalue-getmanagedcopy-method.md)|Obsoleto. Non chiamare questo metodo.|  
|[Metodo GetVirtualMethod](icordebugobjectvalue-getvirtualmethod-method.md)|Non implementato.|  
|[Metodo IsValueClass](icordebugobjectvalue-isvalueclass-method.md)|Ottiene un valore che indica se l'oggetto a cui fa riferimento `ICorDebugObjectValue` è un tipo di valore.|  
|[Metodo SetFromManagedCopy](icordebugobjectvalue-setfrommanagedcopy-method.md)|Obsoleto. Non chiamare questo metodo.|  
  
## <a name="remarks"></a>Osservazioni  
 Un `ICorDebugObjectValue` rimane valido fino a quando il processo di cui è in corso il debug non viene continuato.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
