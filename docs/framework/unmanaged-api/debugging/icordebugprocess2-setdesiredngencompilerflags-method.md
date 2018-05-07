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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ba2b0cf7d88104eaadd434732edf3c1d4060e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a>Metodo ICorDebugProcess2::SetDesiredNGENCompilerFlags
Imposta i flag che devono essere incorporati in un'immagine precompilata affinché il runtime caricare l'immagine nel processo corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pdwFlags`  
 [in] Il valore di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione che specifica i flag del compilatore utilizzata per selezionare l'immagine di pre-compilata corretta.  
  
## <a name="remarks"></a>Note  
 Il `SetDesiredNGENCompilerFlags` metodo specifica i flag che devono essere incorporati in un'immagine precompilata in modo che il runtime di caricarla in questo processo. I flag impostati da questo metodo vengono utilizzati solo per selezionare l'immagine precompilata corretta. Se l'immagine non esiste, il runtime caricherà invece l'immagine di Microsoft intermediate language (MSIL) e il compilatore di just-in-time (JIT). In tal caso, il debugger deve comunque utilizzare il [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) per impostare i flag come desiderato per la compilazione JIT.  
  
 Se viene caricata un'immagine, ma alcuni compilazione JIT deve essere eseguita per questa immagine (che sarà il caso se l'immagine contiene generics), i flag del compilatore specificati da di `SetDesiredNGENCompilerFlags` metodo verrà applicato a compilazione JIT aggiuntiva.  
  
 Il `SetDesiredNGENCompilerFlags` metodo deve essere chiamato durante la [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback. Tenta di chiamare il `SetDesiredNGENCompilerFlags` metodo successivamente avrà esito negativo. Inoltre, i tentativi di impostare i flag che non sono definite nel `CorDebugJITCompilerFlags` enumerazione o che non sono consentiti per il processo specificato avranno esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebug](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [Interfaccia ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
