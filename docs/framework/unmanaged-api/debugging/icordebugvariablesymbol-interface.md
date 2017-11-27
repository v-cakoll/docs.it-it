---
title: Interfaccia ICorDebugVariableSymbol
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 0e58b85e-69bd-41ff-bedb-8cdc8be6a7a2
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 89bae73e9dfb729e26f54dc7874418163870dc27
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvariablesymbol-interface"></a>Interfaccia ICorDebugVariableSymbol
Recupera le informazioni relative al simbolo di debug per una variabile.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetName (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getname-method.md)|Ottiene il nome di una variabile.|  
|[GetSize (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getsize-method.md)|Ottiene le dimensioni di una variabile in byte.|  
|[Metodo GetSlotIndex](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getslotindex-method.md)|Ottiene l'indice dello slot gestito di una variabile locale.|  
|[GetValue (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-getvalue-method.md)|Ottiene il valore di una variabile come matrice di byte.|  
|[SetValue (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-setvalue-method.md)|Assegna il valore di una matrice di byte a una variabile.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
