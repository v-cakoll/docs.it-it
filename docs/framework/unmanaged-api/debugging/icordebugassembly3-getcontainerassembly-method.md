---
title: Metodo ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 068a08d70f2443edfe0970ec1ffb8cba9953c6b9
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894843"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>Metodo ICorDebugAssembly3::GetContainerAssembly
Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppAssembly`  
 Puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly del contenitore oppure **null** se la chiamata al metodo ha esito negativo.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`Se la chiamata al metodo ha esito positivo; in caso `S_FALSE`contrario, `ppAssembly` , e è **null**.  
  
## <a name="remarks"></a>Osservazioni  
 Se l'assembly è stato unito ad altri assembly in un singolo assembly del contenitore, il metodo restituisce l'assembly del contenitore. Per ulteriori informazioni e terminologia, vedere l'argomento [Metodo icordebugprocess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugAssembly3](icordebugassembly3-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
