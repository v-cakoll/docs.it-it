---
title: Interfaccia ICorDebugMutableDataTarget
ms.date: 03/30/2017
ms.assetid: 14aad5b3-84ab-4bbc-94e3-1eb92e258d10
ms.openlocfilehash: 682e927388d3392d970338314f97d46c9e57e760
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139332"
---
# <a name="icordebugmutabledatatarget-interface"></a>Interfaccia ICorDebugMutableDataTarget
Estende l'interfaccia [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) per supportare destinazioni dati modificabili.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ContinueStatusChanged](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-continuestatuschanged-method.md)|Modifica lo stato di continuazione per l'evento di debug in sospeso sul thread specificato.|  
|[Metodo SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-setthreadcontext-method.md)|Imposta il contesto (valori del registro) per un thread.|  
|[Metodo WriteVirtual](../../../../docs/framework/unmanaged-api/debugging/icordebugmutabledatatarget-writevirtual-method.md)|Scrive dalla memoria nello spazio degli indirizzi del processo di destinazione.|  
  
## <a name="remarks"></a>Note  
 Questa estensione per l'interfaccia [ICorDebugDataTarget](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md) può essere implementata da strumenti di debug che vogliono modificare il processo di destinazione (ad esempio, per eseguire il debug invasivo Live).  
  
 Tutti questi metodi sono facoltativi. Se infatti non si implementa questa interfaccia o si verifica un errore durante le chiamate a questi metodi, non si perde alcuna funzionalità principale di debug basata su ispezione.  Qualsiasi `HRESULT` di errore di questi metodi verrà propagato all'esterno come `HRESULT` della chiamata al metodo ICorDebug.  
  
 Si noti che una sola chiamata al metodo ICorDebug può restituire più modifiche e non esistono meccanismi che assicurano che le modifiche correlate vengano applicate in modo transazionale (tutte o nessuna).  Se quindi una modifica non riesce dopo che altre (per la stessa chiamata a ICorDebug) hanno avuto esito positivo, il processo di destinazione potrà rimanere in uno stato incoerente e il debug potrà diventare inaffidabile.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
