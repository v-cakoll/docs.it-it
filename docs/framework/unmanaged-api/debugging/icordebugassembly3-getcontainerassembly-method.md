---
title: Metodo ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e4cda67145a0e624f87e93cf02ebdb6bc77c34d2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69987598"
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
  
## <a name="remarks"></a>Note  
 Se l'assembly è stato unito ad altri assembly in un singolo assembly del contenitore, il metodo restituisce l'assembly del contenitore. Per ulteriori informazioni e terminologia, vedere l'argomento [Metodo icordebugprocess6:: EnableVirtualModuleSplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) .  
  
> [!NOTE]
> Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
