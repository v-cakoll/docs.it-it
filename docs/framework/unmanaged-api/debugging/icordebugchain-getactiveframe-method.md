---
title: Metodo ICorDebugChain::GetActiveFrame
ms.date: 03/30/2017
api_name:
- ICorDebugChain.GetActiveFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugChain::GetActiveFrame
helpviewer_keywords:
- ICorDebugChain::GetActiveFrame method [.NET Framework debugging]
- GetActiveFrame method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 36887017-670b-4f21-b406-8fab956f84a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a104d4d3cc74a6c1cb343818c9b0b3e8978b97df
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402799"
---
# <a name="icordebugchaingetactiveframe-method"></a>Metodo ICorDebugChain::GetActiveFrame
Ottiene attivo (vale a dire più recente) frame sulla catena.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppFrame`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugFrame che rappresenta l'attivo (vale a dire più recente) frame sulla catena.  
  
## <a name="remarks"></a>Note  
 Se non è disponibile alcun frame dello stack gestito `ppFrame` è impostato su null.  
  
 Se il frame attivo non è disponibile, la chiamata avrà esito positivo e `ppFrame` sarà null. Non sarà disponibili per le catene avviate da CHAIN_ENTER_UNMANAGED e per alcune catene avviate CHAIN_CLASS_INIT frame attivi. Vedere l'enumerazione CorDebugChainReason.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
