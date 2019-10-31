---
title: Interfaccia ICorDebugVariableSymbol
ms.date: 03/30/2017
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
ms.openlocfilehash: 25ffa55eeeb82d6feaf5696ea96dae81774e3d70
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121906"
---
# <a name="icordebugvariablesymbol-interface"></a>Interfaccia ICorDebugVariableSymbol
Recupera le informazioni relative al simbolo di debug per una variabile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|Ottiene il nome di una variabile.|  
|[Metodo GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|Ottiene le dimensioni di una variabile in byte.|  
|[Metodo GetSlotIndex](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|Ottiene l'indice dello slot gestito di una variabile locale.|  
|[Metodo GetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|Ottiene il valore di una variabile come matrice di byte.|  
|[Metodo SetValue](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|Assegna il valore di una matrice di byte a una variabile.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
