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
ms.openlocfilehash: c79f3b3b976b83eb99f8aa26d38a1fe316de471a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744991"
---
# <a name="icordebugchaingetactiveframe-method"></a>Metodo ICorDebugChain::GetActiveFrame
Ottiene attivo (vale a dire più recente) frame della catena.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetActiveFrame (  
    [out] ICorDebugFrame   **ppFrame  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppFrame`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugFrame rappresenta attivo (vale a dire più recente) frame della catena.  
  
## <a name="remarks"></a>Note  
 Se non è disponibile alcun stack frame gestito `ppFrame` è impostato su null.  
  
 Se il frame attivo non è disponibile, la chiamata avrà esito positivo e `ppFrame` sarà null. Non sarà disponibili per catene avviate da CHAIN_ENTER_UNMANAGED e per alcuni catene avviate da CHAIN_CLASS_INIT frame attivi. Vedere l'enumerazione CorDebugChainReason.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
