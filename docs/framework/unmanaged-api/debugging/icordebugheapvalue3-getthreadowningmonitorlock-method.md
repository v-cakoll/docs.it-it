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
ms.openlocfilehash: 8be7c0e32f6183deb354d8b3936ef55c2520fe9f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788614"
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
|S_OK|Il metodo è stato eseguito correttamente.|  
|S_FALSE|Nessun thread gestito è proprietario del blocco di monitoraggio per questo oggetto.|  
  
## <a name="exceptions"></a>Eccezioni  
  
## <a name="remarks"></a>Note  
 Se un thread gestito è proprietario del blocco di monitoraggio su questo oggetto:  
  
- Il metodo restituisce S_OK.  
  
- L'oggetto thread è valido fino alla chiusura del thread.  
  
 Se nessun thread gestito è proprietario del blocco di monitoraggio su questo oggetto, `ppThread` e `pAcquisitionCount` sono invariati e il metodo restituisce S_FALSE.  
  
 Se `ppThread` o `pAcquisitionCount` non è un puntatore valido, il risultato è indefinito.  
  
 Se si verifica un errore in modo che non sia possibile determinare quale thread è proprietario del blocco di monitoraggio su questo oggetto, il metodo restituisce un valore HRESULT che indica un errore.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
