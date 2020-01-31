---
title: Metodo ICorDebugFunction3::GetActiveReJitRequestILCode
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugFunction3.GetActiveReJitRequestILCode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 88584574-ade5-45b2-9778-489ed5c4dd7f
topic_type:
- apiref
ms.openlocfilehash: 70a55b833acb7fa946c694a63e1e8b51562938bc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777736"
---
# <a name="icordebugfunction3getactiverejitrequestilcode-method"></a>Metodo ICorDebugFunction3::GetActiveReJitRequestILCode
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Ottiene un puntatore a interfaccia a un [ICorDebugILCode](icordebugilcode-interface.md) che contiene il il da una richiesta ReJIT attiva.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetActiveReJitRequestILCode(  
   ICorDebugILCode **ppReJitedILCode  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppReJitedILCode`  
 Puntatore al linguaggio intermedio (IL) da una richiesta ReJIT attiva.  
  
## <a name="remarks"></a>Note  
 Se il metodo rappresentato da questo oggetto `ICorDebugFunction3` ha una richiesta ReJIT attiva, `ppReJitedILCode` restituisce un puntatore al relativo linguaggio intermedio. Se non sono presenti richieste attive, ovvero un caso comune, `ppReJitedILCode` è **null**.  
  
 Una richiesta ReJIT diventa attiva subito dopo la restituzione dell'esecuzione dalla chiamata al metodo [ICorProfilerCallback4:: GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md) . È possibile che non sia stata ancora sottoposta a compilazione JIT e i thread possono essere ancora in esecuzione nella versione originale del codice. Una richiesta ReJIT diventa inattiva durante la chiamata del profiler al metodo [ICorProfilerInfo4:: RequestRevert](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrevert-method.md) . Anche dopo il ripristino del linguaggio intermedio, un thread può essere ancora in esecuzione nel codice ReJIT.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorDebugFunction3](icordebugfunction3-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
- [ReJIT: Guida alle procedure](https://docs.microsoft.com/archive/blogs/davbr/rejit-a-how-to-guide)
