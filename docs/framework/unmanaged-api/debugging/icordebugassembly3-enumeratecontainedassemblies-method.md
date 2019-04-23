---
title: Metodo ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59080956"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Metodo ICorDebugAssembly3::EnumerateContainedAssemblies
Ottiene un enumeratore per gli assembly contenuti in questo assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppAssemblies`  
 [out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugAssemblyEnum che corrisponde all'enumeratore.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se questo oggetto `ICorDebugAssembly3` è un contenitore, altrimenti `S_FALSE` e l'enumerazione è vuota.  
  
## <a name="remarks"></a>Note  
 I simboli sono necessari per enumerare gli assembly contenuti. Se non ce ne sono, il metodo restituisce `S_FALSE` e non viene fornito alcun enumeratore valido.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
