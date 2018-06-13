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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: eb5145db6f081661996766aab0683dc5d8a97e61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460763"
---
# <a name="icorprofilercallback4movedreferences2-method"></a>Metodo ICorProfilerCallback4::MovedReferences2
Chiamato per segnalare il nuovo layout degli oggetti nell'heap a seguito di un'operazione di Garbage Collection con compattazione. Questo metodo viene chiamato se il profiler ha implementato il [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfaccia. Questo callback sostituisce il [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) metodo, perché può indicare intervalli più ampi di oggetti le cui lunghezze superano quelle che possono essere espresse in ULONG.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT MovedReferences2(  
    [in]  ULONG  cMovedObjectIDRanges,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID oldObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] ObjectID newObjectIDRangeStart[] ,  
    [in, size_is(cMovedObjectIDRanges)] SIZE_T    cObjectIDRangeLength[] );  
```  
  
#### <a name="parameters"></a>Parametri  
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
  
## <a name="remarks"></a>Note  
 Un Garbage Collector di compattazione recupera la memoria occupata dagli oggetti inutilizzati e compatta lo spazio liberato. Gli oggetti attivi possono quindi essere spostati all'interno dell'heap e i valori di `ObjectID` distribuiti dalle notifiche precedenti possono cambiare.  
  
 Si supponga che un valore `ObjectID` esistente (`oldObjectID`) rientri nell'intervallo seguente:  
  
 `oldObjectIDRangeStart[i]` <= `oldObjectID` < `oldObjectIDRangeStart[i]` + `cObjectIDRangeLength[i]`  
  
 In questo caso, l'offset dall'inizio dell'intervallo all'inizio dell'oggetto è il seguente:  
  
 `oldObjectID` - `oldObjectRangeStart[i]`  
  
 Per qualsiasi valore di `i` compreso nell'intervallo seguente:  
  
 0 <= `i` < `cMovedObjectIDRanges`  
  
 è possibile calcolare il nuovo `ObjectID` come segue:  
  
 `newObjectID` = `newObjectIDRangeStart[i]` + (`oldObjectID` – `oldObjectIDRangeStart[i]`)  
  
 Nessuno dei valori di `ObjectID` passati da `MovedReferences2` è valido durante il callback vero e proprio, perché è possibile che il Garbage Collector stia ancora spostando gli oggetti dalle vecchie posizioni a quelle nuove. I profiler non devono quindi tentare di verificare gli oggetti durante una chiamata a `MovedReferences2`. Oggetto [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback indica che tutti gli oggetti sono stati spostati nelle nuove posizioni e possa eseguire l'ispezione.  
  
 Se il profiler implementa sia il [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) e [ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md) interfacce, la `MovedReferences2` metodo viene chiamato prima di [ICorProfilerCallback:: MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md) (metodo), ma solo se il `MovedReferences2` metodo ha esito positivo. I profiler possono restituire un valore HRESULT indicante un errore nel metodo `MovedReferences2` per evitare di chiamare il secondo metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)  
 [Interfaccia ICorProfilerCallback4](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
