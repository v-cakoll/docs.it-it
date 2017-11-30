---
title: Metodo ICorProfilerInfo3::GetAppDomainsContainingModule
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetAppDomainsContainingModule Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetAppDomainsContainingModule
helpviewer_keywords:
- GetAppDomainsContainingModule method [.NET Framework profiling]
- ICorProfilerInfo3::GetAppDomainsContainingModule method [.NET Framework profiling]
ms.assetid: 603b3881-ea94-4dca-95cd-91eebac873a0
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ff9f63fc004d7249b571d980561171464e74b9a2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getappdomainscontainingmodule-method"></a>Metodo ICorProfilerInfo3::GetAppDomainsContainingModule
Ottiene gli identificatori dei domini dell'applicazione in cui è stato caricato il modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetAppDomainsContainingModule(  
            [in] ModuleID moduleId,  
            [in] ULONG32 cAppDomainIds,  
            [out] ULONG32 *pcAppDomainIds,  
            [out, size_is(cAppDomainIds), length_is(*pcAppDomainIds)]  
                    AppDomainID appDomainIds[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] ID del modulo caricato.  
  
 `cAppDomainIds`  
 [in] Dimensione della matrice `appDomainIds`.  
  
 `pcAppDomainIds`  
 [out] Puntatore al numero complessivo di elementi restituiti.  
  
 `appDomainIds`  
 [out] Matrice di valori di valori di ID del dominio applicazione.  
  
## <a name="remarks"></a>Note  
 Il metodo usa buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorProfilerFunctionEnum (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)  
 [ICorProfilerInfo3 (interfaccia)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
