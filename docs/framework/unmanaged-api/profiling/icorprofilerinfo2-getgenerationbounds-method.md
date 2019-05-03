---
title: Metodo ICorProfilerInfo2::GetGenerationBounds
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetGenerationBounds
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19288b5631fea8865530f936ac6d77c0286ee169
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61791684"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a>Metodo ICorProfilerInfo2::GetGenerationBounds
Ottiene le aree di memoria, ovvero i segmenti dell'heap, che costituiscono le diverse generazioni di Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `cObjectRanges`  
 [in] Numero di elementi allocati dal chiamante per la matrice `ranges`.  
  
 `pcObjectRanges`  
 [out] Puntatore a un intero che specifica il numero complessivo di intervalli restituiti, interamente o in parte, nella matrice `ranges`.  
  
 `ranges`  
 [out] Matrice di [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) strutture, ognuno dei quali descrive un intervallo (vale a dire, blocco) di memoria all'interno della generazione viene sottoposto a garbage collection.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetGenerationBounds` può essere chiamato da qualsiasi callback del profiler, purché non sia in corso un'operazione di Garbage Collection. Vale a dire, può essere chiamato da qualsiasi callback a eccezione di quelli che si verificano tra [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) e [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).  
  
 La maggior parte delle modifiche di generazione si verifica durante le operazioni di Garbage Collection. Le generazioni possono aumentare tra un'operazione di Garbage Collection e l'altra, ma in genere non si spostano. I punti più interessanti in cui chiamare `GetGenerationBounds` sono quindi `ICorProfilerCallback2::GarbageCollectionStarted` e `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
 Durante l'avvio del programma, alcuni oggetti vengono allocati direttamente da Common Language Runtime, di solito nelle generazioni 3 e 0. In questo modo, prima che inizi l'esecuzione del codice gestito, queste generazioni conterranno già oggetti. Le generazioni 1 e 2 in genere restano vuote, a eccezione degli oggetti fittizi generati dal Garbage Collector. Le dimensioni degli oggetti fittizi è pari a 12 byte nelle implementazioni a 32 bit di Common Language Runtime, mentre sono maggiori nelle implementazioni a 64 bit. È anche possibile visualizzare gli intervalli di generazione 2 all'interno dei moduli prodotti dal generatore di immagini native (NGen.exe). In questo caso, gli oggetti nella generazione 2 vengono *oggetti bloccati*, che vengono allocate quando viene eseguito NGen.exe piuttosto che dal garbage collector.  
  
 Questa funzione usa buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
