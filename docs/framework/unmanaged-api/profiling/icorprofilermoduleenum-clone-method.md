---
title: Metodo ICorProfilerModuleEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Clone Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Clone
helpviewer_keywords:
- Clone method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Clone method [.NET Framework profiling]
ms.assetid: 7dec7e36-8d88-416d-b437-abf98b76c1df
topic_type:
- apiref
ms.openlocfilehash: ccbb051ac30fb25199ce12c16fff74bb0b9944fa
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495086"
---
# <a name="icorprofilermoduleenumclone-method"></a>Metodo ICorProfilerModuleEnum::Clone
Ottiene un puntatore a interfaccia a una copia di questa interfaccia [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT Clone([out] ICorProfilerObjectEnum **ppEnum);  
```  
  
## <a name="parameters"></a>Parametri  
 `ppEnum`  
 out Puntatore al puntatore a interfaccia che a sua volta punta alla copia dell'interfaccia [ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md) . La copia dell'enumeratore mantiene il proprio stato di enumerazione separatamente da questo enumeratore. Tuttavia, la posizione iniziale del cursore della copia corrisponde alla posizione corrente del cursore dell'enumeratore.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerModuleEnum](icorprofilermoduleenum-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
