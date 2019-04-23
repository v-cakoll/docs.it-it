---
title: Interfaccia ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 015085cff23028814937dfef9aea19af7438b4f5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173810"
---
# <a name="icordebugclass2-interface"></a>Interfaccia ICorDebugClass2

Rappresenta una classe generica oppure una classe con un parametro di metodo di tipo <xref:System.Type>. Questa interfaccia estende [ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetParameterizedType](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-getparameterizedtype-method.md)|Ottiene la dichiarazione del tipo per questa classe.|  
|[Metodo SetJMCStatus](../../../../docs/framework/unmanaged-api/debugging/icordebugclass2-setjmcstatus-method.md)|Per ogni metodo di questa classe, imposta un valore che indica se il metodo è codice definito dall'utente.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [ICorDebugClass (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
