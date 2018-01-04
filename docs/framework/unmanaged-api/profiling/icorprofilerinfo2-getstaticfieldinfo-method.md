---
title: Metodo ICorProfilerInfo2::GetStaticFieldInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStaticFieldInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 8a13a07aeb90d7ad05ca83bf273fe999b9a81bd2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>Metodo ICorProfilerInfo2::GetStaticFieldInfo
Ottiene un valore che indica il tipo di valore statico che si applica al campo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classId`  
 [in] L'ID della classe in cui è definito il campo statico.  
  
 `fieldToken`  
 [in] Il token di metadati per il campo statico.  
  
 `pFieldInfo`  
 [out] Un puntatore a un valore di [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumerazione che indica se il campo specificato è statico, e se in tal caso, il tipo di valore statico che si applica al campo.  
  
## <a name="remarks"></a>Note  
 Queste informazioni è utilizzabile per determinare quale funzione chiamare per ottenere l'indirizzo del campo statico.  
  
 Il codice del profiler deve comunque verificare i metadati per un campo statico per assicurarsi che sia effettivamente un indirizzo. Valori letterali statici (ovvero, costanti) esistono solo nei metadati e non hanno un indirizzo.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
