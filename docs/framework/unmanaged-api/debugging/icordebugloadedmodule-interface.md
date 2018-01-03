---
title: Interfaccia ICorDebugLoadedModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 34be6369-2e75-4a95-a538-3b29ac97cf6d
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4cc7a36deb7c81ccf67427b833dead7127619b39
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugloadedmodule-interface"></a>Interfaccia ICorDebugLoadedModule
Vengono fornite informazioni su un modulo caricato.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetBaseAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getbaseaddress-method.md)|Ottiene l'indirizzo di base del modulo caricato.|  
|[Metodo GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getname-method.md)|Ottiene il nome del modulo caricato.|  
|[Metodo GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugloadedmodule-getsize-method.md)|Ottiene le dimensioni, in byte, del modulo caricato.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugLoadedModule` viene implementata da un debugger e viene usata dalle interfacce di debug CLR per ottenere informazioni sul modulo caricato dal debugger.  
  
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
