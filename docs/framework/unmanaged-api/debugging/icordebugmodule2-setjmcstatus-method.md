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
ms.openlocfilehash: a0b70078dee88b270d8361aa9bddcb7d80df1db1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129465"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>Metodo ICorDebugModule2::SetJMCStatus
Imposta lo stato del Just My Code (JMC) di tutti i metodi di tutte le classi di questo ICorDebugModule2 sul valore specificato, ad eccezione di quelli nella matrice `pTokens`, che imposta sul valore opposto.  
  
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
 in Impostare su `true` se il codice deve essere sottoposto a debug; in caso contrario, impostare su `false`.  
  
 `cTokens`  
 [in] Dimensione della matrice `pTokens`.  
  
 `pTokens`  
 in Matrice di valori di `mdToken`, ciascuno dei quali fa riferimento a un metodo per il quale lo stato del JMC è impostato su.`bIsJustMycode`.  
  
## <a name="remarks"></a>Note  
 Lo stato JMC di ogni metodo specificato nella matrice `pTokens` viene impostato sull'opposto del valore `bIsJustMycode`. Lo stato di tutti gli altri metodi in questo modulo è impostato sul valore `bIsJustMycode`.  
  
 Il metodo `SetJMCStatus` Cancella tutte le impostazioni JMC precedenti in questo modulo.  
  
 Il metodo `SetJMCStatus` restituisce un HRESULT S_OK se tutte le funzioni sono state impostate correttamente. Restituisce un HRESULT CORDBG_E_FUNCTION_NOT_DEBUGGABLE se alcune funzioni contrassegnate come `true` non sono sottoponibili a debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
