---
title: Metodo ICorDebugFunction2::GetVersionNumber
ms.date: 03/30/2017
api_name:
- ICorDebugFunction2.GetVersionNumber
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6cc9c2af62184c83857b82445941f6087a05c2c3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995606"
---
# <a name="icordebugfunction2getversionnumber-method"></a>Metodo ICorDebugFunction2::GetVersionNumber
Ottiene la versione di modifica e continuazione di questa funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnVersion`  
 [out] Un puntatore a un integer che rappresenta il numero di versione della funzione rappresentata dall'oggetto ICorDebugFunction2.  
  
## <a name="remarks"></a>Note  
 Il runtime tiene traccia del numero di modifiche che sono state apportate a ogni modulo durante una sessione di debug. Il numero di versione di una funzione è una maggiore del numero della modifica che è stata introdotta la funzione. La versione della funzione originale è la versione 1. Il numero viene incrementato ogni volta che per un modulo [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) viene chiamato su tale modulo. Di conseguenza, se il corpo della funzione è stato sostituito nella chiamata al prima e il terza `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` potrebbe restituire la versione 1, 2 o 4 per tale funzione, ma non la versione 3. (Tale funzione non potrebbe avere alcuna versione 3).  
  
 Il numero di versione viene registrato separatamente per ogni modulo. Pertanto, se si eseguono quattro modifiche nel modulo 1 e nessuna nel modulo 2, la successiva modifica su 1 modulo assegnerà un numero di versione 6 per tutte le funzioni modificate nel modulo 1. Se le stesse modifiche interessano modulo 2, le funzioni nel modulo 2 otterrà un numero di versione 2.  
  
 Il numero di versione ottenuto mediante la `GetVersionNumber` metodo potrebbe essere inferiore a quello ottenuto da [GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 Il [GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metodo esegue la stessa operazione `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
