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
ms.openlocfilehash: 2358cee1b3a9aa50fb1f0e61d558f164a39aa86c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137354"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a>Metodo ICorDebugModule2::SetJITCompilerFlags
Imposta i flag che controllano la compilazione JIT (just-in-Time) di questo ICorDebugModule2.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `dwFlags`  
 in Combinazione bit per bit dei valori dell'enumerazione [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Note  
 Se il valore `dwFlags` non è valido, il `SetJITCompilerFlags` metodo avrà esito negativo.  
  
 Il metodo `SetJITCompilerFlags` può essere chiamato solo dall'interno del callback [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) per questo modulo. Il tentativo di chiamare questo oggetto dopo il recapito `ICorDebugManagedCallback::LoadModule` callback avrà esito negativo.  
  
 La funzionalità modifica e continuazione non è supportata nelle piattaforme Win9x o a 64 bit. Se pertanto si chiama il metodo `SetJITCompilerFlags` su una di queste due piattaforme con il flag CORDEBUG_JIT_ENABLE_ENC impostato in `dwFlags`, il metodo `SetJITCompilerFlags` e tutti i metodi specifici per la modifica e la continuazione, ad esempio [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), avranno esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
