---
title: Metodo ICorDebugChain::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f050a3d9d37e43713c40896fb162bcf9932c6512
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33403370"
---
# <a name="icordebugchaingetcallee-method"></a>Metodo ICorDebugChain::GetCallee
Ottiene la catena di chiamata da questa catena.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppChain`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di chiamata. Se la catena è attualmente in esecuzione (ovvero, se la catena non è in attesa di una catena di chiamata), `ppChain` sarà null.  
  
## <a name="remarks"></a>Note  
 Questa catena dovrà attendere la catena di chiamata restituire prima di riprendere l'esecuzione. La catena di chiamate potrebbe essere in un altro thread nel caso di chiamate di marshalling cross-thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
