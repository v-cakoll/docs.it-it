---
title: Metodo ICorDebugModule::EnableClassLoadCallbacks
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule.EnableClassLoadCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9045cceda54e6fe89c8c1baa8d4b9fa63105607
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>Metodo ICorDebugModule::EnableClassLoadCallbacks
Controlli se il [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bClassLoadCallbacks`  
 [in] Impostare questo valore su `true` per abilitare common language runtime (CLR) di chiamare il `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` metodi quando si verificano gli eventi associati.  
  
 Il valore predefinito è `false` per i moduli non dinamici. Il valore è sempre `true` per i moduli dinamici e non può essere modificato.  
  
## <a name="remarks"></a>Note  
 Il `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` callback sono sempre abilitati per i moduli dinamici e non può essere disabilitato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
    
 
