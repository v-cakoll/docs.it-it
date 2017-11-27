---
title: Metodo ICorDebugFunction3::GetActiveReJitRequestILCode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugFunction3.GetActiveReJitRequestILCode
api_location: mscordbi.dll
api_type: COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 6459297a2a04728ca87801bfc8484acec384a45c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>Metodo ICorDebugFunction3::GetActiveReJitRequestILCode
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Ottiene un puntatore a interfaccia a un [ICorDebugILCode](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md) che contiene il linguaggio intermedio da una richiesta ReJIT attiva.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `ppReJitedILCode`  
 Puntatore al linguaggio intermedio (IL) da una richiesta ReJIT attiva.  
  
## <a name="remarks"></a>Note  
 Se il metodo rappresentato da questo oggetto `ICorDebugFunction3` ha una richiesta ReJIT attiva, `ppReJitedILCode` restituisce un puntatore al relativo linguaggio intermedio. Se non vi è nessuna richiesta attiva, ovvero un caso comune, quindi `ppReJitedILCode` è **null**.  
  
 Una richiesta ReJIT diventa attiva subito dopo l'esecuzione terminerà il [icorprofilercallback4:: Getrejitparameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) chiamata al metodo. È possibile che non sia stata ancora sottoposta a compilazione JIT e i thread possono essere ancora in esecuzione nella versione originale del codice. Una richiesta ReJIT diventa inattiva durante la chiamata del profiler per il [icorprofilerinfo4:: Requestrevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) metodo. Anche dopo il ripristino del linguaggio intermedio, un thread può essere ancora in esecuzione nel codice ReJIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, Cordebug. H  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorDebugFunction3](../../../../docs/framework/unmanaged-api/debugging/icordebugfunction3-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [ReJIT: Una Guida dettagliata](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
