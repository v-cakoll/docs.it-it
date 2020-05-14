---
title: Interfaccia ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 59ecf3da4b44af7b04dec26fbc3ea182c185d04a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396446"
---
# <a name="icordebugvirtualunwinder-interface"></a>Interfaccia ICorDebugVirtualUnwinder
Fornisce metodi che facilitano lo svuotamento dello stack.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Nome|  
|------------|----------|  
|[Metodo GetContext](icordebugvirtualunwinder-getcontext-method.md)|Ottiene il contesto corrente di questo agente di rimozione.|  
|[Metodo Next](icordebugvirtualunwinder-next-method.md)|Avanza fino al contesto del chiamante.|  
  
## <a name="remarks"></a>Commenti  
 I membri dell'interfaccia `ICorDebugVirtualUnwinder` sono implementati dal debugger per agevolare lo svuotamento dello stack.  
  
> [!NOTE]
> Questa interfaccia è disponibile solo con .NET Native. Se questa interfaccia viene implementata per scenari ICorDebug al di fuori di .NET Native, sarà ignorata da Common Language Runtime.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedi anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
