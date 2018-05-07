---
title: Metodo ICorDebugChain::GetCaller
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCaller
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCaller
helpviewer_keywords:
- ICorDebugChain::GetCaller method [.NET Framework debugging]
- GetCaller method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: d0b8ab4b-d7d2-4fa0-945f-3d2b87e7e991
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1a0b5d702e9718ce6ac537beae67fc190b152b9f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugchaingetcaller-method"></a>Metodo ICorDebugChain::GetCaller
Ottiene la catena che ha chiamato questa catena.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppChain`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di chiamata.  
  
 Se la catena è stata chiamata spontaneamente (come sarebbe se la catena o il debugger inizializzato lo stack di chiamate), `ppChain` sarà null.  
  
## <a name="remarks"></a>Note  
 La catena di chiamata potrebbe essere in un thread differente, se è stato effettuato il marshalling della chiamata tra thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
