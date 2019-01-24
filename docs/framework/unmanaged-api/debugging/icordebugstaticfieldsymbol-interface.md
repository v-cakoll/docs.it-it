---
title: Interfaccia ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0415e622ebba76d0af7d58fc3b59c4bdb47e0043
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54619889"
---
# <a name="icordebugstaticfieldsymbol-interface"></a>Interfaccia ICorDebugStaticFieldSymbol
Rappresenta le informazioni relative al simbolo di debug per un campo statico.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getaddress-method.md)|Ottiene l'indirizzo del campo statico.|  
|[Metodo GetName](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getname-method.md)|Ottiene il nome del campo statico.|  
|[Metodo GetSize](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-getsize-method.md)|Ottiene le dimensioni in byte del campo statico|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorDebugStaticFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo statico.  
  
> [!NOTE]
>  Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorDebugInstanceFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebuginstancefieldsymbol-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
