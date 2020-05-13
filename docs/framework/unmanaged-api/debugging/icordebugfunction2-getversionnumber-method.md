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
ms.openlocfilehash: f47263872b1baf1038a5fa9816c96e3e2569e705
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83213218"
---
# <a name="icordebugfunction2getversionnumber-method"></a>Metodo ICorDebugFunction2::GetVersionNumber
Ottiene la versione di modifica e continuazione di questa funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetVersionNumber (  
    [out] ULONG32   *pnVersion  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pnVersion`  
 out Puntatore a un intero che rappresenta il numero di versione della funzione rappresentata da questo oggetto ICorDebugFunction2.  
  
## <a name="remarks"></a>Osservazioni  
 Il runtime tiene traccia del numero di modifiche che si sono verificate per ogni modulo durante una sessione di debug. Il numero di versione di una funzione è uno più del numero della modifica che ha introdotto la funzione. La versione originale della funzione è la versione 1. Il numero viene incrementato per un modulo ogni volta che viene chiamato [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md) sul modulo. Pertanto, se il corpo di una funzione è stato sostituito nella prima e terza chiamata a `ICorDebugModule2::ApplyChanges` , `GetVersionNumber` può restituire la versione 1, 2 o 4 per tale funzione, ma non la versione 3. Questa funzione non avrebbe la versione 3.  
  
 Il numero di versione viene rilevato separatamente per ogni modulo. Quindi, se si eseguono quattro modifiche sul modulo 1 e nessuna sul modulo 2, la modifica successiva nel modulo 1 assegnerà un numero di versione di 6 a tutte le funzioni modificate nel modulo 1. Se la stessa modifica tocca il modulo 2, le funzioni nel modulo 2 otterranno il numero di versione 2.  
  
 Il numero di versione ottenuto dal `GetVersionNumber` metodo può essere inferiore a quello ottenuto da [ICorDebugFunction:: GetCurrentVersionNumber](icordebugfunction-getcurrentversionnumber-method.md).  
  
 Il metodo [ICorDebugCode:: GetVersionNumber](icordebugcode-getversionnumber-method.md) esegue la stessa operazione di `ICorDebugFunction2::GetVersionNumber` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
