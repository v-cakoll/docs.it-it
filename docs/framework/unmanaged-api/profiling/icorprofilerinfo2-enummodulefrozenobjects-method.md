---
title: Metodo ICorProfilerInfo2::EnumModuleFrozenObjects
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
ms.openlocfilehash: 27b3037459ac4f995e37515f6e96c28449c80a4f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862945"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a>Metodo ICorProfilerInfo2::EnumModuleFrozenObjects
Ottiene un enumeratore che consente l'iterazione sugli oggetti bloccati nel modulo specificato. Questo metodo è obsoleto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleID`  
 in ID del modulo che contiene gli oggetti bloccati da enumerare.  
  
 `ppEnum`  
 out Puntatore all'indirizzo di un'interfaccia [ICorProfilerObjectEnum](icorprofilerobjectenum-interface.md) , che enumera gli oggetti bloccati.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 3,5, 3,0 sp1, 3,0, 2,0 SP1, 2,0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
