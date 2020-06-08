---
title: Interfaccia ICorProfilerModuleEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum
api_location:
- mscorwks.cll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum
helpviewer_keywords:
- ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: 24d0fcfa-1601-4fba-868f-da8c97303467
topic_type:
- apiref
ms.openlocfilehash: fe11c0bbe273ae07cdae43f681a558e07a291ffb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494891"
---
# <a name="icorprofilermoduleenum-interface"></a>Interfaccia ICorProfilerModuleEnum
Fornisce metodi che consentono di eseguire l'iterazione sequenziale con una raccolta di moduli caricati dall'applicazione o dal profiler.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](icorprofilermoduleenum-clone-method.md)|Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerModuleEnum`.|  
|[Metodo GetCount](icorprofilermoduleenum-getcount-method.md)|Ottiene il numero di moduli gestiti caricati nell'applicazione.|  
|[Metodo Next](icorprofilermoduleenum-next-method.md)|Ottiene il numero specificato di moduli contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.|  
|[Metodo Reset](icorprofilermoduleenum-reset-method.md)|Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.|  
|[Metodo Skip](icorprofilermoduleenum-skip-method.md)|Sposta in avanti il cursore dell'enumeratore, in modo che venga ignorato il numero specificato di elementi.|  
  
## <a name="remarks"></a>Osservazioni  
 L'interfaccia `ICorProfilerModuleEnum` è un enumeratore. Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore. In altre parole, il ricevitore è in grado di controllare in modo esplicito il flusso degli elementi della matrice, evitando così i problemi associati al passaggio di matrici di grandi dimensioni come parametri di metodo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Metodo EnumModules](icorprofilerinfo3-enummodules-method.md)
