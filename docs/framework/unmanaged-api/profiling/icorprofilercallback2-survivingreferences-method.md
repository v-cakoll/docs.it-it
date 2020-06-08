---
title: Metodo ICorProfilerCallback2::SurvivingReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.SurvivingReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::SurvivingReferences
helpviewer_keywords:
- ICorProfilerCallback2::SurvivingReferences method [.NET Framework profiling]
- SurvivingReferences method [.NET Framework profiling]
ms.assetid: f165200e-3a91-47f7-88fc-13ff10c8babc
topic_type:
- apiref
ms.openlocfilehash: 3681106bca94f1fefb2f24a1aa4254eb2b1b0531
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499740"
---
# <a name="icorprofilercallback2survivingreferences-method"></a>Metodo ICorProfilerCallback2::SurvivingReferences
Indica il layout degli oggetti nell'heap in seguito a un'operazione di Garbage Collection senza compattazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SurvivingReferences(  
    [in] ULONG  cSurvivingObjectIDRanges,  
    [in, size_is(cSurvivingObjectIDRanges)] ObjectID  
                objectIDRangeStart[] ,  
    [in, size_is(cSurvivingObjectIDRanges)] ULONG  
                cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parametri  
 `cSurvivingObjectIDRanges`  
 [in] Numero di blocchi di oggetti contigui rimasti in seguito alla mancata compattazione dell'operazione di Garbage Collection, ovvero il valore di `cSurvivingObjectIDRanges` è la dimensione delle matrici `objectIDRangeStart` e `cObjectIDRangeLength`, in cui vengono rispettivamente archiviati un `ObjectID` e una lunghezza per ogni blocco di oggetti.  
  
 I successivi due argomenti di `SurvivingReferences` sono matrici parallele. In altre parole, `objectIDRangeStart` e `cObjectIDRangeLength` riguardano lo stesso blocco di oggetti contigui.  
  
 `objectIDRangeStart`  
 [in] Matrice di valori `ObjectID`, ognuno dei quali è l'indirizzo iniziale di un blocco di oggetti attivi contigui in memoria.  
  
 `cObjectIDRangeLength`  
 [in] Matrice di Integer, ognuno dei quali è la dimensione di un blocco escluso di oggetti contigui in memoria.  
  
 Viene specificata una dimensione per ogni blocco a cui si fa riferimento nella matrice `objectIDRangeStart`.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> Questo metodo segnala le dimensioni come `MAX_ULONG` per gli oggetti maggiori di 4 GB su piattaforme a 64 bit. Per gli oggetti più grandi di 4 GB, usare invece il metodo [ICorProfilerCallback4:: SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md) .  
  
 Gli elementi delle matrici `objectIDRangeStart` e `cObjectIDRangeLength` devono essere interpretati come indicato di seguito per determinare se un oggetto è stato escluso dall'operazione di Garbage Collection. Si supponga che un valore `ObjectID` (`ObjectID`) si trovi nell'intervallo seguente:  
  
 `ObjectIDRangeStart[i]` <= `ObjectID` < `ObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 Per qualsiasi valore di `i` compreso nell'intervallo seguente, l'oggetto è stato escluso dall'operazione di Garbage Collection:  
  
 0 <=`i` < `cSurvivingObjectIDRanges`  
  
 Una mancata compattazione dell'operazione di Garbage Collection recupera la memoria occupata dagli oggetti inutilizzati, ma non compatta lo spazio liberato. Di conseguenza, la memoria viene restituita all'heap, ma gli oggetti attivi non vengono spostati.  
  
 Common Language Runtime (CLR) chiama `SurvivingReferences` per eseguire operazioni di Garbage Collection senza compattazione. Per la compattazione di Garbage Collection, viene invece chiamato [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) . Una stessa operazione di Garbage Collection può eseguire la compattazione per una generazione e non eseguirla per un'altra. Per una Garbage Collection in una determinata generazione, il profiler riceverà un callback `SurvivingReferences` o un callback `MovedReferences`, ma non entrambi.  
  
 Durante una particolare operazione di Garbage Collection possono essere ricevuti più callback `SurvivingReferences`, a causa del buffer interno limitato, di callback multipli durante l'operazione di Garbage Collection per server e di altri motivi. Nel caso di più callback durante un'operazione di Garbage Collection, le informazioni sono cumulative. Tutti i riferimenti segnalati in qualsiasi callback `SurvivingReferences` vengono esclusi dall'operazione di Garbage Collection.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Interfaccia ICorProfilerCallback2](icorprofilercallback2-interface.md)
- [Metodo SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md)
