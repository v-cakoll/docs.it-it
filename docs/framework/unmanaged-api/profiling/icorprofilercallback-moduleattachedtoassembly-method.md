---
title: Metodo ICorProfilerCallback::ModuleAttachedToAssembly
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ModuleAttachedToAssembly
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly
helpviewer_keywords:
- ICorProfilerCallback::ModuleAttachedToAssembly method [.NET Framework profiling]
- ModuleAttachedToAssembly method [.NET Framework profiling]
ms.assetid: b595798a-5d40-4cac-ab4f-911c61d2c5d2
topic_type:
- apiref
ms.openlocfilehash: d229b530062d759ab270612fa70b1799acbcadbe
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448066"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>Metodo ICorProfilerCallback::ModuleAttachedToAssembly
Notifica al profiler che un modulo viene collegato al relativo assembly padre.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 in ID del modulo che viene collegato.  
  
 `AssemblyId`  
 in ID dell'assembly padre a cui è collegato il modulo.  
  
## <a name="remarks"></a>Note  
 Un modulo può essere caricato tramite una tabella di indirizzi di importazione (IAT), tramite una chiamata a `LoadLibrary`o tramite un riferimento ai metadati. Di conseguenza, il caricatore di Common Language Runtime (CLR) ha più percorsi di codice per determinare l'assembly in cui risiede un modulo. Di conseguenza, è possibile che dopo la chiamata a [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) il modulo non conosca l'assembly in cui si trova e non sia possibile ottenere l'ID dell'assembly padre. Il metodo `ModuleAttachedToAssembly` viene chiamato quando il modulo viene collegato al relativo assembly padre ed è possibile ottenere il relativo ID assembly padre.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
