---
title: Metodo ICorDebugFunction2::SetJMCStatus
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.SetJMCStatus
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::SetJMCStatus
helpviewer_keywords:
- ICorDebugFunction2::SetJMCStatus method [.NET Framework debugging]
- SetJMCStatus method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: 22c27b01-2869-4214-b840-5921f7c874fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49ced1b4be888c7550c3927d1b319ab2f0bef086
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763776"
---
# <a name="icordebugfunction2setjmcstatus-method"></a>Metodo ICorDebugFunction2::SetJMCStatus
Contrassegna la funzione rappresentata da ICorDebugFunction2 per Just My Code l'esecuzione di istruzioni.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetJMCStatus (  
    [in] BOOL   bIsJustMyCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `bIsJustMyCode`  
 [in] Impostare su `true` per contrassegnare la funzione come codice utente; in caso contrario, impostato su `false`.  
  
## <a name="return-values"></a>Valori restituiti  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|`S_OK`|La funzione è stata contrassegnata.|  
|`CORDBG_E_FUNCTION_NOT_DEBUGGABLE`|La funzione non può essere contrassegnata come codice utente perché non è possibile eseguire il debug.|  
  
## <a name="remarks"></a>Note  
 Un Just My Code ignorerà il codice non utente. Il codice utente deve essere un subset di debug.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
