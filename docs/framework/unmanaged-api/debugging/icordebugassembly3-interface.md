---
title: Interfaccia ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: deb300ced2ff7a116bd443c9a7b10dcc0b7955ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784536"
---
# <a name="icordebugassembly3-interface"></a>Interfaccia ICorDebugAssembly3
Estende logicamente l'interfaccia ICorDebugAssembly per fornire supporto per l'assembly del contenitore e per gli assembly contenuti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateContainedAssemblies](icordebugassembly3-enumeratecontainedassemblies-method.md)|Ottiene un enumeratore per gli assembly contenuti in questo assembly.|  
|[Metodo GetContainerAssembly](icordebugassembly3-getcontainerassembly-method.md)|Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
> L'interfaccia è disponibile solo con .NET Native. Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
