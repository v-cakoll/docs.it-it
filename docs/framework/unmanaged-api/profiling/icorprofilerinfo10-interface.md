---
title: Interfaccia ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 30179c7c198a343baa3fa01ae64f6d580a3f9e7e
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452201"
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

## <a name="requirements"></a>Requisiti  
**Piattaforme:** Vedere [sistemi operativi supportati da .NET Core](../../../core/install/dependencies.md?pivots=os-windows).  
**Intestazione:** CorProf.idl, CorProf.h  
**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
