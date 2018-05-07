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
ms.openlocfilehash: 7ba09991e9452a86c6b7a1cbb08a38a71ba2aeaa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
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
 [out] Il numero di volte in cui che il thread sarebbe necessario rilasciare il blocco prima di restituire a essere senza proprietario.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|S_FALSE|Nessun thread gestito possiede il blocco di monitoraggio su questo oggetto.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Se un thread gestito possiede il blocco di monitoraggio per questo oggetto:  
  
-   Il metodo restituisce S_OK.  
  
-   L'oggetto thread è valido fino a quando non si esce dal thread.  
  
 Se nessun thread gestito possiede il blocco di monitoraggio su questo oggetto `ppThread` e `pAcquisitionCount` sono identiche, e il metodo restituisce S_FALSE.  
  
 Se `ppThread` o `pAcquisitionCount` non è un puntatore valido, il risultato è indefinito.  
  
 Se si verifica un errore che non è possibile determinare che, se presente, thread proprietario del blocco di monitoraggio per questo oggetto, il metodo restituisce un HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
