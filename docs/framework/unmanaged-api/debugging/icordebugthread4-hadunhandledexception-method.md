---
title: Metodo ICorDebugThread4::HadUnhandledException
ms.date: 03/30/2017
api_name:
- ICorDebugThread4.HadUnhandledException Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type:
- apiref
ms.openlocfilehash: 4d954057c519263da49f8aaeeeef6ab9402b6956
ms.sourcegitcommit: d6bd7903d7d46698e9d89d3725f3bb4876891aa3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "83378366"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>Metodo ICorDebugThread4::HadUnhandledException
Indica se il thread ha già avuto un'eccezione non gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a>Parametri  
 `ppBlockingObjectEnum`  
 out Puntatore all'indirizzo di un'enumerazione ordinata di strutture [CorDebugBlockingObject](cordebugblockingobject-structure.md) .  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Description|  
|-------------|-----------------|  
|S_OK|Si è verificata un'eccezione non gestita dal thread dopo la relativa creazione.|  
|S_FALSE|Il thread non ha mai avuto un'eccezione non gestita.|  
  
## <a name="remarks"></a>Osservazioni  
 Questo metodo indica se il thread ha mai avuto un'eccezione non gestita. Al momento dell'attivazione del callback di eccezione non gestita o dell'avvio della connessione JIT nativa, questo metodo garantisce che venga restituito S_OK. Non esiste alcuna garanzia che il metodo [ICorDebugThread. GetCurrentException](icordebugthread-getcurrentexception-method.md) restituisca l'eccezione non gestita. Tuttavia, se il processo non è ancora stato proseguito dopo aver ricevuto il callback di eccezione non gestita o dopo la connessione JIT nativa. Inoltre, è possibile, anche se improbabile, avere più di un thread con un'eccezione non gestita al momento dell'attivazione della connessione JIT nativa. In tal caso non è possibile determinare l'eccezione che ha attivato la connessione JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugThread4](icordebugthread4-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [Debug](index.md)
