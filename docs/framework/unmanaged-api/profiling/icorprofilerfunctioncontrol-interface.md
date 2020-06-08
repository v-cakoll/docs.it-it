---
title: Interfaccia ICorProfilerFunctionControl
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl
helpviewer_keywords:
- ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: 4e3d3141-4662-4166-8f05-bc857c1b4216
topic_type:
- apiref
ms.openlocfilehash: 177127c8c53e4fee31f7007d04c49cc337cca458
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498726"
---
# <a name="icorprofilerfunctioncontrol-interface"></a>Interfaccia ICorProfilerFunctionControl
Fornisce i metodi che consentono a un Code Profiler di comunicare con Common Language Runtime (CLR) per controllare in che modo il compilatore JIT deve generare codice durante la ricompilazione di uno specifico metodo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo SetCodegenFlags](icorprofilerfunctioncontrol-setcodegenflags-method.md)|Imposta uno o più flag dall'enumerazione [COR_PRF_CODEGEN_FLAGS](cor-prf-codegen-flags-enumeration.md) per controllare la generazione di codice per una funzione JIT (just-in-Time) ricompilata.|  
|[Metodo SetILFunctionBody](icorprofilerfunctioncontrol-setilfunctionbody-method.md)|Sostituisce il corpo Common Intermediate Language (CIL) del metodo.|  
|[Metodo SetILInstrumentedCodeMap](icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md)|Imposta una mappa del codice per la funzione specificata usando le voci della mappa CIL (Common Intermediate Language) specificate.|  
  
## <a name="remarks"></a>Osservazioni  
 L'interfaccia `ICorProfilerFunctionControl` fornisce metodi per controllare la generazione di codice per una singola funzione ricompilata. Il profiler ottiene un'istanza di questa interfaccia tramite il callback [ICorProfilerCallback4:: GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md) . Ogni istanza di `ICorProfilerFunctionControl` controlla tutte le istanze di una funzione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Metodo EnumJITedFunctions2](icorprofilerinfo4-enumjitedfunctions2-method.md)
