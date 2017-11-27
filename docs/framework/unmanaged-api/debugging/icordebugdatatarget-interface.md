---
title: Interfaccia ICorDebugDataTarget
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget
helpviewer_keywords: ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: df5f05be-bed7-4f3c-bc89-dbb435d79a0b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 030ad5e61d215bd840da5b16a56e4b8f8b7791ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatarget-interface"></a>Interfaccia ICorDebugDataTarget
Fornisce un'interfaccia di callback che consente di accedere a un determinato processo di destinazione.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetPlatform (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md)|Vengono fornite informazioni sulla piattaforma, tra cui architettura del processore e il sistema operativo, in cui viene eseguito il processo di destinazione.|  
|[ReadVirtual (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-readvirtual-method.md)|Ottiene un blocco di memoria contigua a partire dall'indirizzo specificato e lo restituisce nel buffer fornito.|  
|[GetThreadContext (metodo)](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getthreadcontext-method.md)|Le richieste nel contesto del thread corrente per il thread specificato.|  
  
## <a name="remarks"></a>Note  
 `ICorDebugDataTarget`e i metodi hanno le caratteristiche seguenti:  
  
-   I servizi di debug chiamare metodi su questa interfaccia per accedere a memoria e altri dati nel processo di destinazione.  
  
-   Il client del debugger deve implementare questa interfaccia in modo appropriato per la particolare destinazione (ad esempio, un processo reale o un'immagine della memoria).  
  
-   Il `ICorDebugDataTarget` metodi possono essere richiamati solo dai metodi implementati in altro `ICorDebug*` interfacce. In questo modo si garantisce che il client del debugger dispone di controllo su quale thread viene richiamato in e quando.  
  
-   Il `ICorDebugDataTarget` implementazione deve restituire sempre le informazioni aggiornate sulla destinazione.  
  
 Il processo di destinazione deve essere arrestato e non è stato modificato in alcun modo durante `ICorDebug*` interfacce (e pertanto `ICorDebugDataTarget` metodi) vengono chiamati. Se la destinazione è un processo reale e il relativo stato cambia, il [ICLRDebugging:: OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) metodo deve essere chiamato di nuovo per fornire un'istanza di ICorDebugProcess sostitutiva.  
  
> [!NOTE]
>  Questa interfaccia non supporta la chiamata in modalità remota, tra computer o tra processi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Debug](../../../../docs/framework/unmanaged-api/debugging/index.md)
