---
title: Interfaccia ICorDebugMutableDataTarget
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ef1c0b7a56f6bd1f7e87650b72dfe8b1411ef7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmutabledatatarget-interface"></a>Interfaccia ICorDebugMutableDataTarget
Estende il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia per supportare le destinazioni dati modificabili.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ContinueStatusChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.|  
|[SetThreadContext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|Imposta il contesto (valori del registro) per un thread.|  
|[Metodo WriteVirtual](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.|  
  
## <a name="remarks"></a>Note  
 Questa estensione per il [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) interfaccia può essere implementata da strumenti di debug che vogliono modificare il processo di destinazione (ad esempio, per eseguire debug attivo invasivo).  
  
 Tutti questi metodi sono facoltativi. Se infatti non si implementa questa interfaccia o si verifica un errore durante le chiamate a questi metodi, non si perde alcuna funzionalità principale di debug basata su ispezione.  Qualsiasi `HRESULT` di errore di questi metodi verrà propagato all'esterno come `HRESULT` della chiamata al metodo ICorDebug.  
  
 Si noti che una sola chiamata al metodo ICorDebug può restituire più modifiche e non esistono meccanismi che assicurano che le modifiche correlate vengano applicate in modo transazionale (tutte o nessuna).  Se quindi una modifica non riesce dopo che altre (per la stessa chiamata a ICorDebug) hanno avuto esito positivo, il processo di destinazione potrà rimanere in uno stato incoerente e il debug potrà diventare inaffidabile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
