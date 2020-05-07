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
ms.openlocfilehash: a6d26924773e6ad505975402ec3ace150d02cc3a
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894610"
---
# <a name="icordebugchaingetcaller-method"></a>Metodo ICorDebugChain::GetCaller
Ottiene la catena che ha chiamato questa catena.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppChain`  
 out Puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena chiamante.  
  
 Se questa catena è stata chiamata spontaneamente (come nel caso in cui la catena o il debugger ha inizializzato lo stack di `ppChain` chiamate), sarà null.  
  
## <a name="remarks"></a>Osservazioni  
 La catena chiamante può trovarsi in un thread diverso, se la chiamata è stata sottoposta a marshalling tra thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
