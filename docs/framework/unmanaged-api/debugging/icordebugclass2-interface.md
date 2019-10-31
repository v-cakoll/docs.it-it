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
ms.openlocfilehash: cb2ab28824d209dd1eed627600e30e9ddb0d7c7a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125714"
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
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugClass](../../../../docs/framework/unmanaged-api/debugging/icordebugclass-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
