---
title: Metodo ICorDebugModule2::SetJMCStatus
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJMCStatus
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJMCStatus
helpviewer_keywords:
- SetJMCStatus method, ICorDebugModule2 interface [.NET Framework debugging]
- ICorDebugModule2::SetJMCStatus method [.NET Framework debugging]
ms.assetid: 8c6d2089-4dbb-4715-b9e9-2a4491c8c9ce
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca4b53acc69d0a56b94526de0c3b16fd1abde077
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodule2setjmcstatus-method"></a>Metodo ICorDebugModule2::SetJMCStatus
Imposta lo stato JMC Just My Code () di tutti i metodi di tutte le classi in questa interfaccia ICorDebugModule2 sul valore specificato, eccetto quelli presenti il `pTokens` matrice, che vengono impostati sul valore opposto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL                        bIsJustMyCode,  
    [in] ULONG32                     cTokens,  
    [in, size_is(cTokens)] mdToken   pTokens[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `bIsJustMycode`  
 [in] Impostare su `true` se il codice deve essere sottoposto a debug; in caso contrario, impostato su `false`.  
  
 `cTokens`  
 [in] Dimensione della matrice `pTokens`.  
  
 `pTokens`  
 [in] Matrice di `mdToken` valori, ognuno dei quali fa riferimento a un metodo che sarà necessario impostato il relativo stato JMC!`bIsJustMycode`.  
  
## <a name="remarks"></a>Note  
 Lo stato JMC di ogni metodo specificato nella `pTokens` matrice è l'opposto del `bIsJustMycode` valore. Lo stato di tutti gli altri metodi di questo modulo è impostato sul `bIsJustMycode` valore.  
  
 Il `SetJMCStatus` metodo cancella tutte le impostazioni di JMC precedenti in questo modulo.  
  
 Il `SetJMCStatus` metodo restituisce un HRESULT S_OK se tutte le funzioni sono state impostate correttamente. Restituisce un valore HRESULT invece CORDBG_E_FUNCTION_NOT_DEBUGGABLE se alcune funzioni che sono contrassegnati `true` non è possibile eseguire il debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
