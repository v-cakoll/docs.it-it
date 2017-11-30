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
ms.openlocfilehash: b927d065f26a13d496aec8cd6c8cbc69cf3a8bc9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
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
