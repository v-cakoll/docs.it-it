---
title: Interfaccia ICorDebugComObjectValue
ms.date: 03/30/2017
api_name:
- ICorDebugComObjectValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugComObjectValue
helpviewer_keywords:
- ICorDebugComObjectValue interface [.NET Framework debugging]
ms.assetid: 505a7f6c-d92b-42b4-b539-433f5102ea9b
topic_type:
- apiref
ms.openlocfilehash: ed5b39ed4b2a14c071bf23fb04efbad6834e8a9d
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783966"
---
# <a name="icordebugcomobjectvalue-interface"></a>Interfaccia ICorDebugComObjectValue
Fornisce metodi per recuperare le informazioni associate a un Runtime Callable Wrapper (RCW).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetCachedInterfacePointers](icordebugcomobjectvalue-getcachedinterfacepointers-method.md)|Ottiene i puntatori dell'interfaccia raw memorizzati nella cache dell'RCW corrente.|  
|[Metodo GetCachedInterfaceTypes](icordebugcomobjectvalue-getcachedinterfacetypes-method.md)|Fornisce un enumeratore per i tipi di interfaccia a cui è stato assegnato o utilizzato l'oggetto corrente.|  
  
## <a name="remarks"></a>Note  
 Per verificare se un'istanza di un'interfaccia "ICorDebugValue" rappresenta un RCW, un debugger chiama `QueryInterface` su "ICorDebugValue" con `IID_ICorDebugComObjectValue`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
