---
title: Interfaccia ICorProfilerInfo10
ms.date: 08/06/2019
author: davmason
ms.author: davmason
ms.openlocfilehash: 06cce79fbb2b2eb143e77e3c6fda194e47d4f4f3
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928794"
---
# <a name="icorprofilerinfo10-interface"></a>Interfaccia ICorProfilerInfo10

Sottoclasse di [ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md) che fornisce i metodi per modificare la funzione il, le informazioni di query dal runtime e sospendere e riprendere il Runtime.

## <a name="methods"></a>Metodi  

| Metodo|DESCRIZIONE|  
| ------------|-----------------|  
|[Metodo EnumerateObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-enumerateobjectreferences-method.md)|Dato un ObjectID, callback e clientData, enumera ogni riferimento a un oggetto (se presente). |
|[Metodo IsFrozenObject](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-isfrozenobject-method.md)|Dato un ObjectID, determina se l'oggetto si trova in un segmento di sola lettura. |
|[Metodo GetLOHObjectSizeThreshold](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-getlohobjectsizethreshold-method.md)|Ottiene il valore della soglia dell'oggetto LOH configurata. |
|[Metodo RequestReJITWithInliners](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-requestrejitwithinliners-method.md)| ReJITs i metodi richiesti, nonché tutti gli inliner dei metodi richiesti.  |
|[Metodo SuspendRuntime](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-suspendruntime-method.md)| Sospende il runtime senza eseguire un GC. |
|[Metodo ResumeRuntime](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-resumeruntime-method.md)| Riprende il runtime senza eseguire un catalogo globale. |

## <a name="requirements"></a>Requisiti  
**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
**Intestazione:** CorProf. idl, CorProf. h  
**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)] 

## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
