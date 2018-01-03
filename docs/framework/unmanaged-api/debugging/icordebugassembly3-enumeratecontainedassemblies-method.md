---
title: Metodo ICorDebugAssembly3::EnumerateContainedAssemblies
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8633ce497cd282303c46692a942fe5f88be444c3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Metodo ICorDebugAssembly3::EnumerateContainedAssemblies
Ottiene un enumeratore per gli assembly contenuti in questo assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppAssemblies`  
 [out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugAssemblyEnum che è l'enumeratore.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se questo oggetto `ICorDebugAssembly3` è un contenitore, altrimenti `S_FALSE` e l'enumerazione è vuota.  
  
## <a name="remarks"></a>Note  
 I simboli sono necessari per enumerare gli assembly contenuti. Se non ce ne sono, il metodo restituisce `S_FALSE` e non viene fornito alcun enumeratore valido.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
