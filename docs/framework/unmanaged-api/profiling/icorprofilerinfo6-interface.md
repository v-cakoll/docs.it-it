---
title: Interfaccia ICorProfilerInfo6
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo6
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 6f2bb148-1e2b-4e45-a5a5-0ceddc40064b
ms.openlocfilehash: fba57a88cd3af582b4edf0e5bdbf6ac48020c9f7
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495511"
---
# <a name="icorprofilerinfo6-interface"></a>Interfaccia ICorProfilerInfo6
[Supportato in .NET Framework 4,6 e versioni successive]  
  
 Sottoclasse di [ICorProfilerInfo5](icorprofilerinfo5-interface.md) che fornisce un enumeratore per tutti i metodi definiti in un determinato modulo NGen e inline di un metodo specificato.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod](icorprofilerinfo6-enumngenmodulemethodsinliningthismethod-method.md)|Restituisce un enumeratore per tutti i metodi che appartengono a un modulo NGen specificato e che sono inline nel corpo di un determinato metodo.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di profilatura](profiling-interfaces.md)
