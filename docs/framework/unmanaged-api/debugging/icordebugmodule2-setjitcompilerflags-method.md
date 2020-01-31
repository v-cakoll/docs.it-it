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
ms.openlocfilehash: b28e457ea0b51d320581c0fbe36574698081ea36
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792957"
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
 in Combinazione bit per bit dei valori dell'enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) .  
  
## <a name="remarks"></a>Note  
 Se il valore `dwFlags` non è valido, il `SetJITCompilerFlags` metodo avrà esito negativo.  
  
 Il metodo `SetJITCompilerFlags` può essere chiamato solo dall'interno del callback [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) per questo modulo. Il tentativo di chiamare questo oggetto dopo il recapito `ICorDebugManagedCallback::LoadModule` callback avrà esito negativo.  
  
 La funzionalità modifica e continuazione non è supportata nelle piattaforme Win9x o a 64 bit. Se pertanto si chiama il metodo `SetJITCompilerFlags` su una di queste due piattaforme con il flag di CORDEBUG_JIT_ENABLE_ENC impostato in `dwFlags`, il metodo `SetJITCompilerFlags` e tutti i metodi specifici per la modifica e la continuazione, ad esempio [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), avranno esito negativo.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
