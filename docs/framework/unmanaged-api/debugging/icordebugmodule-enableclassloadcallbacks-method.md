---
title: Metodo ICorDebugModule::EnableClassLoadCallbacks
ms.date: 03/30/2017
api_name:
- ICorDebugModule.EnableClassLoadCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::EnableClassLoadCallbacks
helpviewer_keywords:
- ICorDebugModule::EnableClassLoadCallbacks method [.NET Framework debugging]
- EnableClassLoadCallbacks method [.NET Framework debugging]
ms.assetid: 78dad5e4-8e2e-400f-bec3-92ff0205cd82
topic_type:
- apiref
ms.openlocfilehash: 1ca3adf30ad633fcfb10a4b43a435698d2899597
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213530"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>Metodo ICorDebugModule::EnableClassLoadCallbacks
Controlla se i callback [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bClassLoadCallbacks`  
 in Impostare questo valore su `true` per abilitare la Common Language Runtime (CLR) per chiamare i `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` metodi e quando si verificano gli eventi associati.  
  
 Il valore predefinito è `false` per i moduli non dinamici. Il valore è sempre `true` per i moduli dinamici e non può essere modificato.  
  
## <a name="remarks"></a>Osservazioni  
 I `ICorDebugManagedCallback::LoadClass` `ICorDebugManagedCallback::UnloadClass` callback e sono sempre abilitati per i moduli dinamici e non possono essere disabilitati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
