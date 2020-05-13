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
ms.openlocfilehash: 366a48e5f6abd92f0c6f796f40bdd263181da4a8
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213478"
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
 in Valore dell'enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) che specifica i flag del compilatore usati per selezionare l'immagine precompilata corretta.  
  
## <a name="remarks"></a>Osservazioni  
 Il `SetDesiredNGENCompilerFlags` metodo specifica i flag che devono essere incorporati in un'immagine precompilata in modo che il runtime caricherà tale immagine in questo processo. I flag impostati da questo metodo vengono utilizzati solo per selezionare l'immagine precompilata corretta. Se tale immagine non esiste, il runtime caricherà l'immagine Microsoft Intermediate Language (MSIL) e il compilatore just-in-time (JIT). In tal caso, il debugger deve continuare a usare il metodo [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) per impostare i flag come desiderato per la compilazione JIT.  
  
 Se viene caricata un'immagine, ma è necessario che venga eseguita una compilazione JIT per quell'immagine (come nel caso in cui l'immagine contenga generics), i flag del compilatore specificati dal `SetDesiredNGENCompilerFlags` metodo verranno applicati alla compilazione JIT aggiuntiva.  
  
 Il `SetDesiredNGENCompilerFlags` metodo deve essere chiamato durante il callback [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) . Il tentativo di chiamare il metodo in un secondo momento `SetDesiredNGENCompilerFlags` avrà esito negativo. Inoltre, i tentativi di impostare flag che non sono definiti nell' `CorDebugJITCompilerFlags` enumerazione o che non sono validi per il processo specificato avranno esito negativo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebug](icordebug-interface.md)
- [Interfaccia ICorDebugManagedCallback](icordebugmanagedcallback-interface.md)
