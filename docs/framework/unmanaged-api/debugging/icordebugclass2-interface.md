---
title: ICorDebugClass2 Interface1
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
ms.openlocfilehash: 905e88eb2f43850124414a42bb4e729158f9555a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33405385"
---
# <a name="icordebugclass2-interface1"></a>ICorDebugClass2 Interface1
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
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia1 ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
