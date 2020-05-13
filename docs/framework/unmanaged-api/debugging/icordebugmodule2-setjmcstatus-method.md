---
title: Metodo ICorDebugModule2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type:
- apiref
ms.openlocfilehash: d5109043a8601d7997f52e88ea472644f1b9ca03
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83208785"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>Metodo ICorDebugModule2::SetJMCStatus
Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi di questo ICorDebugModule2 sul valore specificato, ad eccezione di quelli nella `pTokens` matrice, che imposta sul valore opposto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIsJustMycode`  
 in Impostare su `true` se è necessario eseguire il debug del codice; in caso contrario, impostare su `false` .  
  
 `cTokens`  
 [in] Dimensione della matrice `pTokens`.  
  
 `pTokens`  
 in Matrice di `mdToken` valori, ognuno dei quali fa riferimento a un metodo che avrà lo stato JMC impostato su! `bIsJustMycode` .  
  
## <a name="remarks"></a>Osservazioni  
 Lo stato JMC di ogni metodo specificato nella `pTokens` matrice è impostato sull'opposto del `bIsJustMycode` valore. Lo stato di tutti gli altri metodi in questo modulo è impostato sul `bIsJustMycode` valore.  
  
 Il `SetJMCStatus` metodo cancella tutte le impostazioni JMC precedenti in questo modulo.  
  
 Il `SetJMCStatus` metodo restituisce un S_OK HRESULT se tutte le funzioni sono state impostate correttamente. Restituisce un CORDBG_E_FUNCTION_NOT_DEBUGGABLE HRESULT se alcune funzioni contrassegnate non sono sottoponibili a `true` debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
