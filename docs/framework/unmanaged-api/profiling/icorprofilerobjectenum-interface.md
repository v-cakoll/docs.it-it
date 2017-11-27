---
title: Interfaccia ICorProfilerObjectEnum
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerObjectEnum
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerObjectEnum
helpviewer_keywords: ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b46f33485a63404f11dc0606e420ec9c3c43f1f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerobjectenum-interface"></a>Interfaccia ICorProfilerObjectEnum
Fornisce metodi per scorrere in sequenza una raccolta di oggetti bloccati generati dal [Ngen.exe (Native Image Generator)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Clone (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-clone-method.md)|Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerObjectEnum`.|  
|[GetCount (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-getcount-method.md)|Ottiene il numero totale di oggetti bloccati nella raccolta.|  
|[Metodo Next](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-next-method.md)|Ottiene il numero specificato di oggetti contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.|  
|[Reset (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-reset-method.md)|Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.|  
|[Metodo Skip](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-skip-method.md)|Sposta il cursore dell'enumeratore dalla posizione corrente in modo che venga ignorato il numero specificato di elementi.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorProfilerObjectEnum` è un enumeratore. Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore. In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi di matrice, evitando così i problemi relativi al passaggio di matrici di grandi dimensioni come parametri di metodo.  
  
 Utilizzare [ICorProfilerInfo2:: EnumModuleFrozenObjects](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md) per ottenere un puntatore per il `ICorProfilerObjectEnum` interfaccia.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [EnumModuleFrozenObjects (metodo)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)
