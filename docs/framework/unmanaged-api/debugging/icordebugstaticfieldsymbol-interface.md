---
title: Interfaccia ICorDebugStaticFieldSymbol
ms.date: 03/30/2017
ms.assetid: c0b93609-631e-4b15-878a-189ede922631
ms.openlocfilehash: f9b82f0f98a668555a8096d7575c049c31cae93a
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83379433"
---
# <a name="icordebugstaticfieldsymbol-interface"></a>Interfaccia ICorDebugStaticFieldSymbol
Rappresenta le informazioni relative al simbolo di debug per un campo statico.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetAddress](icordebugstaticfieldsymbol-getaddress-method.md)|Ottiene l'indirizzo del campo statico.|  
|[Metodo GetName](icordebugstaticfieldsymbol-getname-method.md)|Ottiene il nome del campo statico.|  
|[Metodo GetSize](icordebugstaticfieldsymbol-getsize-method.md)|Ottiene le dimensioni in byte del campo statico|  
  
## <a name="remarks"></a>Osservazioni  
 L'interfaccia `ICorDebugStaticFieldSymbol` viene usata per recuperare le informazioni sul simbolo di debug per un campo statico.  
  
> [!NOTE]
> Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugInstanceFieldSymbol](icordebuginstancefieldsymbol-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
