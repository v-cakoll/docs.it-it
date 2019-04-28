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
ms.openlocfilehash: fd65de77209f5a981c0a4c291f8573a61cf6335b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645279"
---
# <a name="icordebugchaingetcaller-method"></a>Metodo ICorDebugChain::GetCaller
Ottiene la catena che ha chiamato questa catena.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCaller (  
    [out] ICorDebugChain      **ppChain  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppChain`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugChain che rappresenta la catena di chiamata.  
  
 Se questa catena è stata chiamata spontaneamente (come sarebbe il caso se questa catena o il debugger inizializzata nello stack di chiamate), `ppChain` sarà null.  
  
## <a name="remarks"></a>Note  
 La catena di chiamata può essere su un thread diverso, se è stato effettuato il marshalling della chiamata tra thread.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
