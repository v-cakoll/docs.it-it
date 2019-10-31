---
title: Metodo ICorDebugProcess2::SetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
ms.openlocfilehash: 9313fc58dec8099f42dbff07685ca14791fa324f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137167"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>Metodo ICorDebugProcess2::SetDesiredNGENCompilerFlags
Imposta i flag che devono essere incorporati in un'immagine precompilata per consentire al runtime di caricare tale immagine nel processo corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pdwFlags`  
 in Valore dell'enumerazione [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) che specifica i flag del compilatore usati per selezionare l'immagine precompilata corretta.  
  
## <a name="remarks"></a>Note  
 Il metodo `SetDesiredNGENCompilerFlags` specifica i flag che devono essere incorporati in un'immagine precompilata in modo che il runtime caricherà tale immagine in questo processo. I flag impostati da questo metodo vengono utilizzati solo per selezionare l'immagine precompilata corretta. Se tale immagine non esiste, il runtime caricherà l'immagine Microsoft Intermediate Language (MSIL) e il compilatore just-in-time (JIT). In tal caso, il debugger deve continuare a usare il metodo [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) per impostare i flag come desiderato per la compilazione JIT.  
  
 Se viene caricata un'immagine, ma è necessario che venga eseguita una compilazione JIT per tale immagine, come avviene nel caso in cui l'immagine contenga generics, i flag del compilatore specificati dal metodo `SetDesiredNGENCompilerFlags` verranno applicati alla compilazione JIT aggiuntiva.  
  
 Il metodo di `SetDesiredNGENCompilerFlags` deve essere chiamato durante il callback [ICorDebugManagedCallback:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) . I tentativi di chiamare il metodo `SetDesiredNGENCompilerFlags` in un secondo momento avranno esito negativo. Inoltre, i tentativi di impostare flag che non sono definiti nell'enumerazione `CorDebugJITCompilerFlags` o non sono validi per il processo specificato avranno esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
