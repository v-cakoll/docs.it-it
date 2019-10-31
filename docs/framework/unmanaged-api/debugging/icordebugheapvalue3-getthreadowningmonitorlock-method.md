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
ms.openlocfilehash: ec265525d01dab0669939569501fce91b500a900
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127497"
---
# <a name="icordebugheapvalue3getthreadowningmonitorlock-method"></a>Metodo ICorDebugHeapValue3::GetThreadOwningMonitorLock
Restituisce il thread gestito proprietario del blocco di monitoraggio su questo oggetto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetThreadOwningMonitorLock (  
    [out] ICorDebugThread   **ppThread,  
    [out] DWORD              *pAcquisitionCount  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppThread`  
 out Thread gestito proprietario del blocco di monitoraggio su questo oggetto.  
  
 `pAcquisitionCount`  
 out Il numero di volte in cui il thread deve rilasciare il blocco prima che torni a essere senza proprietario.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Metodo completato correttamente.|  
|S_FALSE|Nessun thread gestito è proprietario del blocco di monitoraggio per questo oggetto.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Se un thread gestito è proprietario del blocco di monitoraggio su questo oggetto:  
  
- Il metodo restituisce S_OK.  
  
- L'oggetto thread è valido fino alla chiusura del thread.  
  
 Se nessun thread gestito è proprietario del blocco di monitoraggio su questo oggetto, `ppThread` e `pAcquisitionCount` sono invariati e il metodo restituisce S_FALSE.  
  
 Se `ppThread` o `pAcquisitionCount` non è un puntatore valido, il risultato è indefinito.  
  
 Se si verifica un errore in modo che non sia possibile determinare quale thread è proprietario del blocco di monitoraggio su questo oggetto, il metodo restituisce un valore HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
