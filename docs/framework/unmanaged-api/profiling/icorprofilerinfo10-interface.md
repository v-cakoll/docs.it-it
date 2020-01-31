---
title: Interfaccia ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: e90a1ffbc037636e4296bbd4f4c3c5082885e9f3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863244"
---
# <a name="icorprofilerinfo10-interface"></a>Interfaccia ICorProfilerInfo10

Sottoclasse di [ICorProfilerInfo9](icorprofilerinfo9-interface.md) che fornisce i metodi per modificare la funzione il, le informazioni di query dal runtime e sospendere e riprendere il Runtime.

## <a name="methods"></a>Metodi  

| Metodo|Descrizione|  
| ------------|-----------------|  
|[Metodo EnumerateObjectReferences](icorprofilerinfo10-enumerateobjectreferences-method.md)|Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente). |
|[Metodo IsFrozenObject](icorprofilerinfo10-isfrozenobject-method.md)|Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura. |
|[Metodo GetLOHObjectSizeThreshold](icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ottiene il valore della soglia dell'oggetto LOH configurata. |
|[Metodo RequestReJITWithInliners](icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs i metodi richiesti, nonché tutti gli inliner dei metodi richiesti.  |
|[Metodo SuspendRuntime](icorprofilerinfo10-suspendruntime-method.md)| Sospende il runtime senza eseguire un GC. |
|[Metodo ResumeRuntime](icorprofilerinfo10-resumeruntime-method.md)| Riprende il runtime senza eseguire un catalogo globale. |

## <a name="requirements"></a>Requisiti di  
**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).  
**Intestazione:** CorProf.idl, CorProf.h  
**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
