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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e6b5281e30c48471131fa12e5106f7d0a6826e1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452559"
---
# <a name="icorprofilercallbackmoduleattachedtoassembly-method"></a>Metodo ICorProfilerCallback::ModuleAttachedToAssembly
Notifica al profiler che un modulo viene allegato a tale assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT ModuleAttachedToAssembly(  
    [in] ModuleID   moduleId,  
    [in] AssemblyID AssemblyId);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'ID del modulo che si sta collegando.  
  
 `AssemblyId`  
 [in] L'ID dell'assembly padre a cui è associato il modulo.  
  
## <a name="remarks"></a>Note  
 Un modulo può essere caricato tramite una tabella di indirizzi di importazione (IAT), tramite una chiamata a `LoadLibrary`, o tramite un riferimento ai metadati. Di conseguenza, il caricatore di common language runtime (CLR) dispone di più percorsi di codice per determinare l'assembly in cui si trova un modulo. Pertanto, è possibile che dopo [ICorProfilerCallback:: ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) viene chiamato, il modulo non sappia quali assembly si trova e l'ID dell'assembly padre non è possibile. Il `ModuleAttachedToAssembly` metodo viene chiamato quando il modulo è connesso al relativo assembly padre ed è possibile ottenere l'ID di tale assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
