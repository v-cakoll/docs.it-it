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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed2364c7c47aed1430a86aeee3daabf6b94cbf3b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754473"
---
# <a name="icordebugfunction2getjmcstatus-method"></a>Metodo ICorDebugFunction2::GetJMCStatus
Ottiene un valore che indica se la funzione rappresentata dall'oggetto ICorDebugFunction2 è contrassegnata come codice utente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetJMCStatus (  
    [out] BOOL   *pbIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbIsJustMyCode`  
 [out] Un puntatore a un valore booleano che è `true`, se questa funzione è contrassegnata come codice utente; in caso contrario, il valore è `false`.  
  
## <a name="remarks"></a>Note  
 Se la funzione rappresentata da questo `ICorDebugFunction2` non è possibile eseguire il debug, `pbIsJustMyCode` sarà sempre `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
