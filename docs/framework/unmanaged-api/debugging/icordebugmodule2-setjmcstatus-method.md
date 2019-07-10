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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d438123dcefb901098954845596c210e5b76cea6
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67764113"
---
# <a name="icordebugmodule2setjmcstatus-method"></a>Metodo ICorDebugModule2::SetJMCStatus
Imposta lo stato di Just My Code (JMC) di tutti i metodi di tutte le classi in questo ICorDebugModule2 sul valore specificato, eccetto quelli presenti il `pTokens` matrice, che imposta il valore opposto.  
  
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
 [in] Impostare su `true` se il codice deve essere sottoposto a debug; in caso contrario, impostato su `false`.  
  
 `cTokens`  
 [in] Dimensione della matrice `pTokens`.  
  
 `pTokens`  
 [in] Matrice di `mdToken` valori, ognuno dei quali fa riferimento a un metodo che avrà lo stato JMC impostato su!`bIsJustMycode`.  
  
## <a name="remarks"></a>Note  
 Lo stato JMC di ogni metodo specificato nel `pTokens` matrice è impostata su opposto di `bIsJustMycode` valore. Lo stato di tutti gli altri metodi in questo modulo viene impostato sul `bIsJustMycode` valore.  
  
 Il `SetJMCStatus` metodo cancella tutte le impostazioni precedenti JMC in questo modulo.  
  
 Il `SetJMCStatus` metodo restituisce un HRESULT S_OK se tutte le funzioni sono state impostate correttamente. Restituisce un HRESULT invece CORDBG_E_FUNCTION_NOT_DEBUGGABLE se alcune funzioni che sono contrassegnate `true` non sono ancora debuggable.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
