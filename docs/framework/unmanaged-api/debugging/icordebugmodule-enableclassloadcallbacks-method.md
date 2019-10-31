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
ms.openlocfilehash: c18ed781d44c873b4cd1957bf0102a4ce0cccad4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139224"
---
# <a name="icordebugmoduleenableclassloadcallbacks-method"></a>Metodo ICorDebugModule::EnableClassLoadCallbacks
Controlla se i callback [ICorDebugManagedCallback:: LoadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md) vengono chiamati per questo modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnableClassLoadCallbacks(  
    [in] BOOL bClassLoadCallbacks  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bClassLoadCallbacks`  
 in Impostare questo valore su `true` per consentire al Common Language Runtime (CLR) di chiamare i metodi di `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` quando si verificano gli eventi associati.  
  
 Il valore predefinito è `false` per i moduli non dinamici. Il valore è sempre `true` per i moduli dinamici e non può essere modificato.  
  
## <a name="remarks"></a>Note  
 I callback `ICorDebugManagedCallback::LoadClass` e `ICorDebugManagedCallback::UnloadClass` sono sempre abilitati per i moduli dinamici e non possono essere disabilitati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
