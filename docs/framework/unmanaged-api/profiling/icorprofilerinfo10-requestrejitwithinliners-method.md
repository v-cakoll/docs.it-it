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
ms.openlocfilehash: 5822136eb1a7f582bcfae901a99775950e586198
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863179"
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

## <a name="parameters"></a>Parametri

- `dwRejitFlags`

  \[in] maschera di [COR_PRF_REJIT_FLAGS](cor-prf-rejit-flags-enumeration.md).

- `cFunctions`

  \[in] numero di funzioni da ricompilare.

- `moduleIds`

  \[in] specifica la parte `moduleId` delle coppie (`module``methodDef`) che identificano le funzioni da ricompilare.

- `methodIds`

  \[in] specifica la parte `methodId` delle coppie (`module``methodDef`) che identificano le funzioni da ricompilare.

## <a name="remarks"></a>Note

[RequestReJIT](icorprofilerinfo4-requestrejit-method.md) non esegue alcun rilevamento dei metodi inline. Il profiler avrebbe dovuto bloccare l'incorporamento o tenere traccia dell'incorporamento e chiamare `RequestReJIT` per tutti gli Inliners per assicurarsi che ogni istanza di un metodo reso inline fosse ReJITted. Si è verificato un problema con ReJIT durante l'associazione, poiché il profiler non è presente per il monitoraggio dell'incorporamento. Questo metodo può essere chiamato per garantire che anche il set completo di inliner sarà ReJITted.

## <a name="requirements"></a>Requisiti di

**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).

**Intestazione:** CorProf.idl, CorProf.h

**Libreria:** CorGuids.lib

**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo10](icorprofilerinfo10-interface.md)
