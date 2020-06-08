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
ms.openlocfilehash: 2e6e3a6432d6568532a5f5b9676b5f130eb83d0b
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502887"
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a>Metodo ICorProfilerInfo2::GetGenerationBounds
Ottiene le aree di memoria, ovvero i segmenti dell'heap, che costituiscono le diverse generazioni di Garbage Collection.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 out Matrice di strutture di [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , ognuna delle quali descrive un intervallo, ovvero un blocco, della memoria all'interno della generazione che è in fase di Garbage Collection.  
  
## <a name="remarks"></a>Osservazioni  
 Il metodo `GetGenerationBounds` può essere chiamato da qualsiasi callback del profiler, purché non sia in corso un'operazione di Garbage Collection.

 La maggior parte delle modifiche di generazione si verifica durante le operazioni di Garbage Collection. Le generazioni possono aumentare tra un'operazione di Garbage Collection e l'altra, ma in genere non si spostano. I punti più interessanti in cui chiamare `GetGenerationBounds` sono quindi `ICorProfilerCallback2::GarbageCollectionStarted` e `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
 Durante l'avvio del programma, alcuni oggetti vengono allocati direttamente da Common Language Runtime, di solito nelle generazioni 3 e 0. In questo modo, prima che inizi l'esecuzione del codice gestito, queste generazioni conterranno già oggetti. Le generazioni 1 e 2 in genere restano vuote, a eccezione degli oggetti fittizi generati dal Garbage Collector. (La dimensione degli oggetti fittizi è 12 byte nelle implementazioni a 32 bit di CLR; le dimensioni sono maggiori nelle implementazioni a 64 bit). È anche possibile vedere gli intervalli di generazione 2 che si trovano all'interno dei moduli prodotti dal generatore di immagini native (NGen. exe). In questo caso, gli oggetti della generazione 2 sono *oggetti bloccati*, che vengono allocati quando viene eseguito Ngen. exe anziché dal Garbage Collector.  
  
 Questa funzione usa buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
