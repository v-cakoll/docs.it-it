---
title: Interfaccia ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 4c5d553744008734037975d6e63e1b07b89cf886
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175070"
---
# <a name="icorprofilerinfo10-interface"></a>Interfaccia ICorProfilerInfo10

Sottoclasse di [ICorProfilerInfo9](icorprofilerinfo9-interface.md) che fornisce metodi per modificare il linguaggio di controllo dell'attivazione delle funzioni, eseguire query sulle informazioni dal runtime e sospendere e riprendere il runtime.

## <a name="methods"></a>Metodi  

| Metodo|Descrizione|  
| ------------|-----------------|  
|[Metodo EnumerateObjectReferences](icorprofilerinfo10-enumerateobjectreferences-method.md)|Dato un ObjectID, callback e clientData, enumera ogni riferimento all'oggetto (se presente). |
|[Metodo IsFrozenObject](icorprofilerinfo10-isfrozenobject-method.md)|Dato un ObjectID, determina se l'oggetto è in un segmento di sola lettura. |
|[Metodo GetLOHObjectSizeThreshold](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ottiene il valore della soglia LOH configurata. |
|[Metodo RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs i metodi richiesti, così come qualsiasi inliner s dei metodi richiesti.  |
|[Metodo SuspendRuntime](icorprofilerinfo10-suspendruntime-method.md)| Sospende il runtime senza eseguire un catalogo globale. |
|[Metodo ResumeRuntime](icorprofilerinfo10-resumeruntime-method.md)| Riprende il runtime senza eseguire un GC. |

## <a name="requirements"></a>Requisiti  
**Piattaforme:** Consultate [Sistemi operativi supportati da .NET Core.](../../../core/install/dependencies.md?pivots=os-windows)  
**Intestazione:** CorProf.idl, CorProf.h  
**Versioni .NET:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
