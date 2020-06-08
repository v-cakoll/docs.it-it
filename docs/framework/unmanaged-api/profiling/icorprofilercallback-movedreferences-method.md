---
title: Metodo ICorProfilerCallback::MovedReferences
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.MovedReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::MovedReferences
helpviewer_keywords:
- MovedReferences method [.NET Framework profiling]
- ICorProfilerCallback::MovedReferences method [.NET Framework profiling]
ms.assetid: 996c71ae-0676-4616-a085-84ebf507649d
topic_type:
- apiref
ms.openlocfilehash: 1214182c95f7d0304ec920a2ea7dae91b1f4a790
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503336"
---
# <a name="icorprofilercallbackmovedreferences-method"></a>Metodo ICorProfilerCallback::MovedReferences
Chiamato per segnalare il nuovo layout degli oggetti nell'heap a seguito di un'operazione di Garbage Collection con compattazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT MovedReferences(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ULONG    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parametri  
 `cMovedObjectIDRanges`  
 [in] Numero di blocchi di oggetti contigui spostati in seguito all'operazione di Garbage Collection con compattazione. Ciò significa che il valore di `cMovedObjectIDRanges` corrisponde alle dimensioni totali delle matrici `oldObjectIDRangeStart`, `newObjectIDRangeStart` e `cObjectIDRangeLength`.  
  
 I successivi tre argomenti di `MovedReferences` sono matrici parallele. In altre parole, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` e `cObjectIDRangeLength[i]` riguardano un singolo blocco di oggetti contigui.  
  
 `oldObjectIDRangeStart`  
 [in] Matrice di valori `ObjectID`, ognuno dei quali è il vecchio indirizzo iniziale (precedente all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.  
  
 `newObjectIDRangeStart`  
 [in] Matrice di valori `ObjectID`, ognuno dei quali è il nuovo indirizzo iniziale (successivo all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.  
  
 `cObjectIDRangeLength`  
 [in] Matrice di Integer, ognuno dei quali corrisponde alle dimensioni di un blocco di oggetti contigui in memoria.  
  
 Viene specificata una dimensione per ogni blocco a cui viene fatto riferimento nelle matrici `oldObjectIDRangeStart` e `newObjectIDRangeStart`.  
  
## <a name="remarks"></a>Osservazioni  
  
> [!IMPORTANT]
> Questo metodo segnala le dimensioni come `MAX_ULONG` per gli oggetti maggiori di 4 GB su piattaforme a 64 bit. Per ottenere le dimensioni degli oggetti maggiori di 4 GB, usare invece il metodo [ICorProfilerCallback4:: MovedReferences2](icorprofilercallback4-movedreferences2-method.md) .  
  
 Un Garbage Collector di compattazione recupera la memoria occupata dagli oggetti inutilizzati e compatta lo spazio liberato. Gli oggetti attivi possono quindi essere spostati all'interno dell'heap e i valori di `ObjectID` distribuiti dalle notifiche precedenti possono cambiare.  
  
 Si supponga che un valore `ObjectID` esistente (`oldObjectID`) rientri nell'intervallo seguente:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 In questo caso, l'offset dall'inizio dell'intervallo all'inizio dell'oggetto è il seguente:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Per qualsiasi valore di `i` compreso nell'intervallo seguente:  
  
 0 <=`i` < `cMovedObjectIDRanges`  
  
 è possibile calcolare il nuovo `ObjectID` come segue:  
  
 `newObjectID` = `newObjectIDRangeStart[i]`+ ( `oldObjectID` - `oldObjectIDRangeStart[i]` )  
  
 Nessuno dei valori di `ObjectID` passati da `MovedReferences` è valido durante il callback vero e proprio, perché è possibile che l'operazione di Garbage Collection stia ancora spostando gli oggetti dalle vecchie posizioni a quelle nuove. I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `MovedReferences`. Un callback [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) indica che tutti gli oggetti sono stati spostati nelle nuove posizioni ed è possibile eseguire il controllo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo MovedReferences2](icorprofilercallback4-movedreferences2-method.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
