---
title: Metodo ICorDebugFunction2::GetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::GetJMCStatus method [.NET Framework debugging]
- GetJMCStatus method [.NET Framework debugging]
ms.assetid: 840a71ed-bf5a-4f5e-8ed6-762222b34493
topic_type:
- apiref
ms.openlocfilehash: 360434fe6e08804d8c80c4ea36d585209cc6761a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137812"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>Metodo ICorDebugFunction2::GetJMCStatus
Ottiene un valore che indica se la funzione rappresentata da questo oggetto ICorDebugFunction2 è contrassegnata come codice utente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbIsJustMyCode`  
 out Puntatore a un valore booleano `true`, se questa funzione è contrassegnata come codice utente; in caso contrario, il valore è `false`.  
  
## <a name="remarks"></a>Note  
 Se non è possibile eseguire il debug della funzione rappresentata da questo `ICorDebugFunction2`, `pbIsJustMyCode` sarà sempre `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
