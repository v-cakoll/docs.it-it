---
title: Metodo ICorDebugModule2::SetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e605859a3049abc0c17d9d6792ade78f4ad2bd78
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>Metodo ICorDebugModule2::SetJITCompilerFlags
Imposta i flag che controllano la compilazione just-in-time (JIT) di questa interfaccia ICorDebugModule2.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `dwFlags`  
 [in] Combinazione bit per bit di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) valori di enumerazione.  
  
## <a name="remarks"></a>Note  
 Se il `dwFlags` valore non è valido, il `SetJITCompilerFlags` metodo avrà esito negativo.  
  
 Il `SetJITCompilerFlags` metodo può essere chiamato solo dall'interno di [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback per questo modulo. Tenta di chiamare dopo il `ICorDebugManagedCallback::LoadModule` callback è stato inviato avranno esito negativo.  
  
 Modifica e continuazione non è supportata in 64 bit o in piattaforme Win9x. Pertanto, se si chiama il `SetJITCompilerFlags` metodo su una di queste due piattaforme con il flag CORDEBUG_JIT_ENABLE_ENC impostato `dwFlags`, `SetJITCompilerFlags` (metodo) e tutti i metodi specifici di modifica e continuazione, ad esempio [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), avrà esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
