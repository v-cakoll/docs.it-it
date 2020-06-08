---
title: Metodo ICorProfilerCallback4::MovedReferences2
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.MovedReferences2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::MovedReferences2
helpviewer_keywords:
- MovedReferences2 method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::MovedReferences2 method [.NET Framework profiling]
ms.assetid: d17a065b-5bc6-4817-b3e1-1e413fcb33a8
topic_type:
- apiref
ms.openlocfilehash: 79e54cde8757bbe690f9b7c4344a2a3cb19cf627
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499383"
---
# <a name="icorprofilercallback4movedreferences2-method"></a>Metodo ICorProfilerCallback4::MovedReferences2
Chiamato per segnalare il nuovo layout degli oggetti nell'heap a seguito di un'operazione di Garbage Collection con compattazione. Questo metodo viene chiamato se il profiler ha implementato l'interfaccia [ICorProfilerCallback4](icorprofilercallback4-interface.md) . Questo callback sostituisce il metodo [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , perché può segnalare intervalli più grandi di oggetti le cui lunghezze superano quelle che possono essere espresse in un ULONG.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
## <a name="parameters"></a>Parametri  
 `cMovedObjectIDRanges`  
 [in] Numero di blocchi di oggetti contigui spostati in seguito all'operazione di Garbage Collection con compattazione. Ciò significa che il valore di `cMovedObjectIDRanges` corrisponde alle dimensioni totali delle matrici `oldObjectIDRangeStart`, `newObjectIDRangeStart` e `cObjectIDRangeLength`.  
  
 I successivi tre argomenti di `MovedReferences2` sono matrici parallele. In altre parole, `oldObjectIDRangeStart[i]`, `newObjectIDRangeStart[i]` e `cObjectIDRangeLength[i]` riguardano un singolo blocco di oggetti contigui.  
  
 `oldObjectIDRangeStart`  
 [in] Matrice di valori `ObjectID`, ognuno dei quali è il vecchio indirizzo iniziale (precedente all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.  
  
 `newObjectIDRangeStart`  
 [in] Matrice di valori `ObjectID`, ognuno dei quali è il nuovo indirizzo iniziale (successivo all'operazione di Garbage Collection) di un blocco di oggetti attivi contigui in memoria.  
  
 `cObjectIDRangeLength`  
 [in] Matrice di Integer, ognuno dei quali corrisponde alle dimensioni di un blocco di oggetti contigui in memoria.  
  
 Viene specificata una dimensione per ogni blocco a cui viene fatto riferimento nelle matrici `oldObjectIDRangeStart` e `newObjectIDRangeStart`.  
  
## <a name="remarks"></a>Osservazioni  
 Un Garbage Collector di compattazione recupera la memoria occupata dagli oggetti inutilizzati e compatta lo spazio liberato. Gli oggetti attivi possono quindi essere spostati all'interno dell'heap e i valori di `ObjectID` distribuiti dalle notifiche precedenti possono cambiare.  
  
 Si supponga che un valore `ObjectID` esistente (`oldObjectID`) rientri nell'intervallo seguente:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 In questo caso, l'offset dall'inizio dell'intervallo all'inizio dell'oggetto è il seguente:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Per qualsiasi valore di `i` compreso nell'intervallo seguente:  
  
 0 <=`i` < `cMovedObjectIDRanges`  
  
 è possibile calcolare il nuovo `ObjectID` come segue:  
  
 `newObjectID` = `newObjectIDRangeStart[i]`+ ( `oldObjectID` - `oldObjectIDRangeStart[i]` )  
  
 Nessuno dei valori di `ObjectID` passati da `MovedReferences2` è valido durante il callback vero e proprio, perché è possibile che il Garbage Collector stia ancora spostando gli oggetti dalle vecchie posizioni a quelle nuove. I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `MovedReferences2`. Un callback [ICorProfilerCallback2:: GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) indica che tutti gli oggetti sono stati spostati nelle nuove posizioni ed è possibile eseguire il controllo.  
  
 Se il profiler implementa entrambe le interfacce [ICorProfilerCallback](icorprofilercallback-interface.md) e [ICorProfilerCallback4](icorprofilercallback4-interface.md) , il `MovedReferences2` metodo viene chiamato prima del metodo [ICorProfilerCallback:: MovedReferences](icorprofilercallback-movedreferences-method.md) , ma solo se il `MovedReferences2` metodo viene restituito correttamente. I profiler possono restituire un valore HRESULT indicante un errore nel metodo `MovedReferences2` per evitare di chiamare il secondo metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](icorprofilercallback-interface.md)
- [Metodo MovedReferences](icorprofilercallback-movedreferences-method.md)
- [Interfaccia ICorProfilerCallback4](icorprofilercallback4-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
