---
title: Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock
ms.date: 03/30/2017
api_name:
- ICorDebugHeapValue3.GetThreadOwningMonitorLock
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapValue3::GetThreadOwningMonitorLock
helpviewer_keywords:
- GetThreadOwningMonitorLock method [.NET Framework debugging]
- ICorDebugHeapValue3::GetThreadOwningMonitorLock method [.NET Framework debugging]
ms.assetid: e06fc19d-2cf4-4cad-81a3-137a68af8969
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8d3e10a3dbae0d1b790c0d80c9286affedaa4c8b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54709143"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock
Restituisce il thread gestito che possiede il blocco di monitoraggio per questo oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppThread`  
 [out] Il thread gestito che possiede il blocco di monitoraggio per questo oggetto.  
  
 `pAcquisitionCount`  
 [out] Il numero di volte in cui che il thread dovrà rilasciare il blocco prima di restituire a essere senza proprietario.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|S_FALSE|Nessun thread gestito possiede il blocco di monitoraggio per questo oggetto.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Se un thread gestito è il proprietario del blocco di monitoraggio per questo oggetto:  
  
-   Il metodo restituisce S_OK.  
  
-   L'oggetto thread è valido fino a quando la chiusura del thread.  
  
 Se nessun thread gestito possiede il blocco di monitoraggio tohoto objektu `ppThread` e `pAcquisitionCount` rimangono invariati, e il metodo restituisce S_FALSE.  
  
 Se `ppThread` o `pAcquisitionCount` non è un puntatore valido, il risultato è indefinito.  
  
 Se si verifica un errore in modo che non può essere determinato che, se presente, thread proprietario del blocco di monitoraggio per l'oggetto, il metodo restituisce un HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
