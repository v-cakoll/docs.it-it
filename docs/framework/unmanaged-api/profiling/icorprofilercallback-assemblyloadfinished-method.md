---
title: Metodo ICorProfilerCallback::AssemblyLoadFinished
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
- ICorProfilerCallback.AssemblyLoadFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AssemblyLoadFinished
helpviewer_keywords:
- ICorProfilerCallback::AssemblyLoadFinished method [.NET Framework profiling]
- AssemblyLoadFinished method [.NET Framework profiling]
ms.assetid: 86d98f39-52e6-4c61-a625-9760f695ff12
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9de280a1b92bc921ecb400c80522f21cf65f861a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackassemblyloadfinished-method"></a>Metodo ICorProfilerCallback::AssemblyLoadFinished
Notifica al profiler che un assembly è stato completato il caricamento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT AssemblyLoadFinished(  
    [in] AssemblyID assemblyId,  
    [in] HRESULT    hrStatus);  
```  
  
#### <a name="parameters"></a>Parametri  
 `assemblyId`  
 [in] Identifica l'assembly caricato.  
  
 `hrStatus`  
 [in] Un valore HRESULT che indica se l'assembly è stato caricato correttamente.  
  
## <a name="remarks"></a>Note  
 Il valore di `assemblyId` non è valido per una richiesta di informazioni fino a quando il `AssemblyLoadFinished` metodo viene chiamato.  
  
 Alcune parti del caricamento dell'assembly potrebbero continuare dopo il `AssemblyLoadFinished` callback. Un HRESULT di errore in `hrStatus` indica un errore. Tuttavia, un HRESULT positivo in `hrStatus` indica solo che la prima parte del caricamento dell'assembly ha avuto esito positivo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
