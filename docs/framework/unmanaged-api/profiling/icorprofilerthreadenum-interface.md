---
title: Interfaccia ICorProfilerThreadEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerThreadEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum
helpviewer_keywords:
- ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: 1e35031b-e095-4c14-9644-8deeb3081e0b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4758d97aab0b4827ba955922c6b14f35ff0f3f81
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerthreadenum-interface"></a>Interfaccia ICorProfilerThreadEnum
Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di funzioni in Common Language Runtime.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-clone-method.md)|Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerThreadEnum`.|  
|[Metodo GetCount](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-getcount-method.md)|Ottiene il numero di thread usati dall'applicazione.|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-next-method.md)|Ottiene il numero specificato di thread contigui da una raccolta sequenziale di moduli, a partire dalla posizione corrente dell'enumeratore nella sequenza.|  
|[Metodo Reset](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-reset-method.md)|Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.|  
|[Metodo Skip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-skip-method.md)|Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che venga ignorato il numero specificato di elementi.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorProfilerThreadEnum` è un enumeratore. Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore. In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi della matrice, evitando così i problemi associati al passaggio di matrici di grandi dimensioni come parametri di metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
