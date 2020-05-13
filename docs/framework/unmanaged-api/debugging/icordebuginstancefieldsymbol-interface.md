---
title: Interfaccia ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 092f2a8acdffa9f91176bdf0ca10b8db9cff6d37
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83209929"
---
# <a name="icordebuginstancefieldsymbol-interface"></a>Interfaccia ICorDebugInstanceFieldSymbol
Rappresenta le informazioni relative al simbolo di debug per un campo di istanza.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetName](icordebuginstancefieldsymbol-getname-method.md)|Ottiene il nome del campo di istanza.|  
|[Metodo GetOffset](icordebuginstancefieldsymbol-getoffset-method.md)|Ottiene l'offset, in byte, di questo campo di istanza nella relativa classe padre.|  
|[Metodo GetSize](icordebuginstancefieldsymbol-getsize-method.md)|Ottiene le dimensioni, in byte, del campo di istanza.|  
  
## <a name="remarks"></a>Osservazioni  
 L'interfaccia `ICorDebugInstanceFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo di istanza.  
  
> [!NOTE]
> Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
