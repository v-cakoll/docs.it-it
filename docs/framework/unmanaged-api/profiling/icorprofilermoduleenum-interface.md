---
title: Interfaccia ICorProfilerModuleEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerModuleEnum
api_location: mscorwks.cll
api_type: COM
f1_keywords: ICorProfilerModuleEnum
helpviewer_keywords: ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 43cc6afc42fc1a02fd7d7b3df2973cc9b3e31251
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilermoduleenum-interface"></a>Interfaccia ICorProfilerModuleEnum
Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Clone (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-clone-method.md)|Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerModuleEnum`.|  
|[GetCount (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-getcount-method.md)|Ottiene il numero di moduli gestiti caricati nell'applicazione.|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-next-method.md)|Ottiene il numero specificato di moduli contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.|  
|[Reset (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-reset-method.md)|Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.|  
|[Metodo Skip](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-skip-method.md)|Sposta in avanti il cursore dell'enumeratore, in modo che venga ignorato il numero specificato di elementi.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorProfilerModuleEnum` è un enumeratore. Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore. In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi della matrice, evitando così i problemi associati al passaggio di matrici di grandi dimensioni come parametri di metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumModules (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)
