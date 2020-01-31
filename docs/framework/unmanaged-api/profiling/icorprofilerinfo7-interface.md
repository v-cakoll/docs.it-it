---
title: Interfaccia ICorProfilerInfo7
ms.date: 03/30/2017
ms.assetid: cf37c462-73c5-412a-a7f8-bb26ca746313
ms.openlocfilehash: f80f310c10bae33583cb7cd2048ede4f5efbe14c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861749"
---
# <a name="icorprofilerinfo7-interface"></a>Interfaccia ICorProfilerInfo7
[Supportata in .NET Framework 4.6.1 e versioni successive]  
  
 Sottoclasse di [ICorProfilerInfo6](icorprofilerinfo6-interface.md) che fornisce un metodo per applicare i metadati appena definiti a un modulo e che fornisce l'accesso a un flusso di simboli in memoria.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ApplyMetaData](icorprofilerinfo7-applymetadata-method.md)|Applica i metadati appena definiti dal `IMetadataEmit::Define*` metodi a un modulo specificato.|  
|[Metodo GetInMemorySymbolsLength](icorprofilerinfo7-getinmemorysymbolslength-method.md)|Restituisce la lunghezza di un flusso di simboli in memoria.|  
|[ReadInMemorySymbols](icorprofilerinfo7-readinmemorysymbols.md)|Legge i byte da un flusso di simboli in memoria.|  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
