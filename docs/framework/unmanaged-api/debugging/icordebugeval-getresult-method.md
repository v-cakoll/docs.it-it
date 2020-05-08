---
title: Metodo ICorDebugEval::GetResult
ms.date: 03/30/2017
api_name:
- ICorDebugEval.GetResult
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval::GetResult
helpviewer_keywords:
- ICorDebugEval::GetResult method [.NET Framework debugging]
- GetResult method [.NET Framework debugging]
ms.assetid: 50dbb9af-58a1-41f4-b56d-3da20011884f
topic_type:
- apiref
ms.openlocfilehash: 2d065d956319076d3b92eddafd4a2c25ffbfbac1
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976265"
---
# <a name="icordebugevalgetresult-method"></a>Metodo ICorDebugEval::GetResult
Ottiene i risultati della valutazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetResult (  
    [out] ICorDebugValue    **ppResult  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppResult`  
 out Puntatore all'indirizzo di un oggetto ICorDebugValue che rappresenta i risultati della valutazione, se la valutazione viene completata normalmente.  
  
## <a name="remarks"></a>Osservazioni  
 Il `GetResult` metodo è valido solo dopo il completamento della valutazione.  
  
 Se la valutazione viene completata normalmente, `ppResult` specifica i risultati. Se termina con un'eccezione, il risultato è l'eccezione generata. Se la valutazione era per un nuovo oggetto, il risultato è il riferimento al nuovo oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
