---
title: Interfaccia ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66d3024c0bb2c0014cbec2b24deb7b0d5845fe88
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627525"
---
# <a name="icordebugassembly3-interface"></a>Interfaccia ICorDebugAssembly3
Estende logicamente l'interfaccia ICorDebugAssembly per fornire il supporto per l'assembly del contenitore e gli assembly contenuti.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumerateContainedAssemblies](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-enumeratecontainedassemblies-method.md)|Ottiene un enumeratore per gli assembly contenuti in questo assembly.|  
|[Metodo GetContainerAssembly](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-getcontainerassembly-method.md)|Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.|  
  
## <a name="remarks"></a>Note  
  
> [!NOTE]
>  L'interfaccia è disponibile solo con .NET Native. Il tentativo di chiamare `QueryInterface` per recuperare un puntatore a interfaccia restituisce `E_NOINTERFACE` per gli scenari ICorDebug al di fuori di .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
