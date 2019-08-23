---
title: Interfaccia ICorDebugDataTarget
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget
helpviewer_keywords:
- ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c6a8ee1bcc65e640ef871e57acdeef21acd7896
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930828"
---
# <a name="icordebugdatatarget-interface"></a>Interfaccia ICorDebugDataTarget
Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|DESCRIZIONE|  
|------------|-----------------|  
|[Metodo GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Fornisce informazioni sulla piattaforma, tra cui l'architettura del processore e il sistema operativo in cui è in esecuzione il processo di destinazione.|  
|[Metodo ReadVirtual](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.|  
|[Metodo GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Richiede il contesto del thread corrente per il thread specificato.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugDataTarget`e i relativi metodi hanno le caratteristiche seguenti:  
  
- I servizi di debug chiamano metodi su questa interfaccia per accedere alla memoria e ad altri dati nel processo di destinazione.  
  
- Il client del debugger deve implementare questa interfaccia in modo appropriato per la destinazione specifica (ad esempio, un processo attivo o un dump della memoria).  
  
- I `ICorDebugDataTarget` metodi possono essere richiamati solo dall'interno dei metodi `ICorDebug*` implementati in altre interfacce. In questo modo si garantisce che il client del debugger disponga del controllo su quale thread viene richiamato e quando.  
  
- L' `ICorDebugDataTarget` implementazione deve sempre restituire informazioni aggiornate sulla destinazione.  
  
 Il processo di destinazione deve essere interrotto e non modificato in alcun modo `ICorDebug*` durante la chiamata di `ICorDebugDataTarget` interfacce (e di conseguenza metodi). Se la destinazione è un processo attivo e il relativo stato viene modificato, è necessario chiamare nuovamente il metodo [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) per fornire un'istanza di ICorDebugProcess sostitutiva.  
  
> [!NOTE]
> Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug. idl, CorDebug. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
