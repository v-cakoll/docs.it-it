---
title: Metodo ICorDebugModule2::ResolveAssembly
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.ResolveAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::ResolveAssembly
helpviewer_keywords:
- ICorDebugModule2::ResolveAssembly method [.NET Framework debugging]
- ResolveAssembly method [.NET Framework debugging]
ms.assetid: ddf9085c-7161-44bd-9609-cd2732b9009f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a6596807b98e6c8b8624b5df18f78dbf8d0711
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodule2resolveassembly-method"></a>Metodo ICorDebugModule2::ResolveAssembly
Consente di risolvere l'assembly a cui fa riferimento il token di metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ResolveAssembly (  
    [in]  mdToken             tkAssemblyRef,  
    [out] ICorDebugAssembly   **ppAssembly  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tkAsemblyRef`  
 [in] Un `mdToken` valore che fa riferimento all'assembly.  
  
 `ppAssembly`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly.  
  
## <a name="remarks"></a>Note  
 Se l'assembly non è già caricato quando `ResolveAssembly` viene chiamato, un valore HRESULT restituito CORDBG_E_CANNOT_RESOLVE_ASSEMBLY.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]
