---
title: Metodo ICorProfilerInfo::GetModuleMetaData
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2491b700e8fac512f0d782a42e30ae3114e93c3f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>Metodo ICorProfilerInfo::GetModuleMetaData
Ottiene un'istanza di interfaccia di metadati che esegue il mapping per il modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'ID del modulo a cui verrà eseguito il mapping l'istanza dell'interfaccia.  
  
 `dwOpenFlags`  
 [in] Il valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione che specifica la modalità di apertura dei file manifesti. Solo il `ofRead`, `ofWrite` e `ofNoTransform` bit sono validi.  
  
 `riid`  
 [in] Il riferimento all'ID (GUID) dell'interfaccia di metadati la cui istanza verrà recuperato. Vedere [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) per un elenco delle interfacce.  
  
 `ppOut`  
 [out] Un puntatore all'indirizzo dell'istanza di interfaccia di metadati.  
  
## <a name="remarks"></a>Note  
 È possibile chiedere che i metadati essere aperto in modalità lettura/scrittura, ma il risultato sarà rallenterà l'esecuzione del programma, perché le modifiche apportate per i metadati non possono essere ottimizzato come avveniva dal compilatore.  
  
 Alcuni moduli (ad esempio, i moduli delle risorse) non hanno metadati. In questi casi, `GetModuleMetaData` restituirà un valore HRESULT di S_FALSE e un valore null in *`ppOut`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
