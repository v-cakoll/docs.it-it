---
title: Metodo ICorDebugFrame::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1b622d1bd82e53d5fa232e07b1f49e6fbba3ccba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugframegetfunction-method"></a>Metodo ICorDebugFrame::GetFunction
Ottiene la funzione che contiene il codice associato a questo stack frame.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppFunction`  
 [out] Un puntatore all'indirizzo di un oggetto ICorDebugFunction che rappresenta la funzione contenente il codice associato a questo stack frame.  
  
## <a name="remarks"></a>Note  
 Il `GetFunction` metodo potrebbe non riuscire se il frame non è associato ad alcuna funzione particolare.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
