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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12433786f353212c1ffbd57e9bf526c3ecc60e9a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59163631"
---
# <a name="icordebugthread4hadunhandledexception-method"></a>Metodo ICorDebugThread4::HadUnhandledException
Indica se il thread è stato mai un'eccezione non gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
## <a name="parameters"></a>Parametri  
 `ppBlockingObjectEnum`  
 [out] Un puntatore all'indirizzo di un'enumerazione di ordinato [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il thread è verificata un'eccezione non gestita dopo la creazione.|  
|S_FALSE|Il thread non è mai stato un'eccezione non gestita.|  
  
## <a name="remarks"></a>Note  
 Questo metodo indica se il thread è stato mai un'eccezione non gestita. Quando viene attivato il callback di eccezione non gestita o native ad associazione JIT viene avviata, questo metodo garantisce la restituzione S_OK. Non c'è garanzia che il [ICorDebugThread. GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) metodo restituirà un'eccezione non gestita; tuttavia, si verifica se il processo non ancora ripreso dopo aver ottenuto il callback di eccezione non gestita o al momento associazione JIT nativa. Inoltre, è possibile (nonostante sia improbabile) che più thread con un'eccezione non gestita al momento native ad associazione JIT viene attivato. In tal caso non è possibile determinare l'eccezione che ha attivato l'associazione JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugThread4](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
