---
title: Metodo ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: acb34ac2568ac88797441306820e6e762b5ac46e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33409727"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a>Metodo ICorDebugAssembly3::GetContainerAssembly
Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppAssembly`  
 Un puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly del contenitore o **null** se la chiamata al metodo ha esito negativo.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` Se la chiamata al metodo ha esito positivo; in caso contrario, `S_FALSE`, e `ppAssembly` viene **null**.  
  
## <a name="remarks"></a>Note  
 Se l'assembly è stato unito ad altri assembly in un singolo assembly del contenitore, il metodo restituisce l'assembly del contenitore. Per ulteriori informazioni e terminologia, vedere il [icordebugprocess6:: Enablevirtualmodulesplitting](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-enablevirtualmodulesplitting-method.md) argomento.  
  
> [!NOTE]
>  Questo metodo è disponibile solo con .NET Native.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
