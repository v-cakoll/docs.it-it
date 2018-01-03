---
title: Metodo ICorDebugFunction2::GetVersionNumber
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction2.GetVersionNumber
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction2::GetVersionNumber
helpviewer_keywords:
- ICorDebugFunction2::GetVersionNumber method [.NET Framework debugging]
- GetVersionNumber method, ICorDebugFunction2 interface [.NET Framework debugging]
ms.assetid: e3a1ce48-9bb9-4ed6-a5fe-5e1819a6333f
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 16902d1a50f691ae555fdbc964bb9a1c6bf563c4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugfunction2getversionnumber-method"></a>Metodo ICorDebugFunction2::GetVersionNumber
Ottiene la versione di modifica e continuazione di questa funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pnVersion`  
 [out] Puntatore a un intero che rappresenta il numero di versione della funzione rappresentata dall'oggetto ICorDebugFunction2.  
  
## <a name="remarks"></a>Note  
 Il runtime tiene traccia del numero di modifiche che sono state apportate a ogni modulo durante una sessione di debug. Il numero di versione di una funzione è superiore al numero della modifica introdotte dalla funzione. La versione della funzione originale è la versione 1. Il numero viene incrementato ogni volta per un modulo [ICorDebugModule2::](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md) viene chiamato su tale modulo. Pertanto, se il corpo di una funzione è stato sostituito nella prima e la terza chiamata a `ICorDebugModule2::ApplyChanges`, `GetVersionNumber` potrebbe restituire la versione 1, 2 o 4 per tale funzione, ma non la versione 3. (Tale funzione non avrebbe la versione 3.)  
  
 Il numero di versione viene registrato separatamente per ogni modulo. In tal caso, se si eseguono quattro modifiche nel modulo 1 e nessuna su modulo 2, la successiva modifica nel modulo 1 assegnerà un numero di versione 6 per tutte le funzioni modificate nel modulo 1. Se le stesse modifiche interessano modulo 2, le funzioni nel modulo 2 verranno visualizzato un numero di versione 2.  
  
 Il numero di versione viene ottenuto il `GetVersionNumber` metodo potrebbe essere inferiore a quello ottenuto da [ICorDebugFunction:: GetCurrentVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction-getcurrentversionnumber-method.md).  
  
 Il [GetVersionNumber](../../../../docs/framework/unmanaged-api/debugging/icordebugcode-getversionnumber-method.md) metodo esegue la stessa operazione `ICorDebugFunction2::GetVersionNumber`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
