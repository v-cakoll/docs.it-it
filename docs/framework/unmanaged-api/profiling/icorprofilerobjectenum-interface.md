---
title: Interfaccia ICorProfilerObjectEnum
ms.date: 03/30/2017
api_name:
- ICorProfilerObjectEnum
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerObjectEnum
helpviewer_keywords:
- ICorProfilerObjectEnum interface [.NET Framework profiling]
ms.assetid: 13e1651c-9523-40ef-bfd7-87fb94519f8b
topic_type:
- apiref
ms.openlocfilehash: fce89cc2b3b0104ba017b7df9105dea3f6ec4e91
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868226"
---
# <a name="icorprofilerobjectenum-interface"></a>Interfaccia ICorProfilerObjectEnum
Fornisce metodi per scorrere in sequenza una raccolta di oggetti bloccati generati da [NGen. exe (Generatore di immagini native)](../../../../docs/framework/tools/ngen-exe-native-image-generator.md).  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo Clone](icorprofilerobjectenum-clone-method.md)|Ottiene un puntatore a interfaccia per una copia di questa interfaccia `ICorProfilerObjectEnum`.|  
|[Metodo GetCount](icorprofilerobjectenum-getcount-method.md)|Ottiene il numero totale di oggetti bloccati nella raccolta.|  
|[Metodo Next](icorprofilerobjectenum-next-method.md)|Ottiene il numero specificato di oggetti contigui da una raccolta sequenziale di oggetti, a partire dalla posizione corrente dell'enumeratore nella sequenza.|  
|[Metodo Reset](icorprofilerobjectenum-reset-method.md)|Sposta il cursore dell'enumeratore nella posizione iniziale della sequenza.|  
|[Metodo Skip](icorprofilerobjectenum-skip-method.md)|Sposta in avanti il cursore dell'enumeratore dalla posizione corrente, in modo che il numero di elementi specificato venga ignorato.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `ICorProfilerObjectEnum` è un enumeratore. Consente al ricevitore di una matrice di effettuare il pull di elementi dal mittente a una velocità appropriata per il ricevitore. In altre parole, il destinatario è in grado di controllare in modo esplicito il flusso degli elementi di matrice, evitando così i problemi correlati al passaggio di matrici di grandi dimensioni come parametri del metodo.  
  
 Usare [ICorProfilerInfo2:: EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md) per ottenere un puntatore all'interfaccia `ICorProfilerObjectEnum`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
- [Metodo EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)
