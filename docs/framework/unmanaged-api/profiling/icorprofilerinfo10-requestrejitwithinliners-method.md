---
title: ICorProfilerInfo10::RequestReJITWithInliners
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.RequestReJITWithInliners
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: c33a868b643cb3e3fd5dfaf436e3078bc590705c
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449814"
---
# <a name="icorprofilerinfo10requestrejitwithinliners-method"></a>Metodo ICorProfilerInfo10:: RequestReJITWithInliners

ReJITs i metodi richiesti, nonché tutti gli inliner dei metodi richiesti.

## <a name="syntax"></a>Sintassi

```cpp
HRESULT RequestReJITWithInliners( [in]                       DWORD       dwRejitFlags,
                                  [in]                       ULONG       cFunctions,
                                  [in, size_is(cFunctions)]  ModuleID    moduleIds[],
                                  [in, size_is(cFunctions)]  mdMethodDef methodIds[]);
```

#### <a name="parameters"></a>Parametri

`dwRejitFlags` \
in Maschera di maschera di [COR_PRF_REJIT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-rejit-flags-enumeration.md).

`cFunctions` \
[in] Numero di funzioni da ricompilare.

`moduleIds` \
[in] Specifica la parte `moduleId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ricompilare.

`methodIds` \
[in] Specifica la parte `methodId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ricompilare.

## <a name="remarks"></a>Osservazioni

[RequestReJIT](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-requestrejit-method.md) non esegue alcun rilevamento dei metodi inline. Il profiler avrebbe dovuto bloccare l'incorporamento o tenere traccia dell'incorporamento e chiamare `RequestReJIT` per tutti gli Inliners per assicurarsi che ogni istanza di un metodo reso inline fosse ReJITted. Si è verificato un problema con ReJIT durante l'associazione, poiché il profiler non è presente per il monitoraggio dell'incorporamento. Questo metodo può essere chiamato per garantire che anche il set completo di inliner sarà ReJITted.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
