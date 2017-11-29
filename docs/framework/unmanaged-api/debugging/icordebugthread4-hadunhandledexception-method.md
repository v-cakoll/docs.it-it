---
title: Metodo ICorDebugThread4::HadUnhandledException
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread4.HadUnhandledException Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread4::HadUnhandledException
helpviewer_keywords:
- ICorDebugThread4::HadUnhandledException method [.NET Framework debugging]
- HadUnhandledException method [.NET Framework debugging]
ms.assetid: 05558daa-39e2-4c38-aeaf-e2aec4a09468
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ea29fa02e74c204cde003b18520bf512b0d21d7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugthread4hadunhandledexception-method"></a>Metodo ICorDebugThread4::HadUnhandledException
Indica se il thread è già verificata un'eccezione non gestita.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetBlockingObjects (  
    [out] ICorDebugBlockingObjectEnum **ppBlockingObjectEnum  
    );  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppBlockingObjectEnum`  
 [out] Un puntatore all'indirizzo di un'enumerazione ordinata di [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) strutture.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|Il thread è verificata un'eccezione non gestita dal momento della creazione.|  
|S_FALSE|Il thread non è stato mai un'eccezione non gestita.|  
  
## <a name="remarks"></a>Note  
 Questo metodo indica se il thread è già verificata un'eccezione non gestita. Quando viene attivato il callback di eccezione non gestita o native ad associazione JIT viene avviato, viene garantito che questo metodo per restituire S_OK. Non c'è garanzia che il [ICorDebugThread. GetCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md) metodo restituirà l'eccezione non gestita; tuttavia, verranno eseguite se il processo non ancora ripreso dopo aver ottenuto il callback di eccezione non gestita o dopo il associazione JIT nativa. Inoltre, è possibile (anche se improbabile) abbia più di un thread con un'eccezione non gestita in fase di associazione JIT nativa viene attivato. In questo caso non è possibile determinare quale eccezione ha attivato l'associazione JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorDebugThread4 (interfaccia)](../../../../docs/framework/unmanaged-api/debugging/icordebugthread4-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
