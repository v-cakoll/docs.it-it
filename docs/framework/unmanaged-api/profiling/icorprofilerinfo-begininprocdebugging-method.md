---
title: Metodo ICorProfilerInfo::BeginInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 330a159e056018d702eec7e4fef80c3d8e041212
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54630801"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a>Metodo ICorProfilerInfo::BeginInprocDebugging
Consente di inizializzare il supporto del debug in-process. Questo metodo è obsoleto in .NET Framework versione 2.0.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fThisThreadOnly`  
 [in] Impostare questo valore su `true` per inizializzare il supporto del debug solo il thread corrente; impostato su `false` per inizializzare il supporto del debug per tutti i thread.  
  
 `pdwProfilerContext`  
 [out] Il puntatore su un valore restituito che identifica la sessione di debug.  
  
## <a name="remarks"></a>Note  
 I servizi di debug CLR supportavano il debug in-process limitata nelle versioni 1.0 e 1.1 di .NET Framework. Per attivare un profiler di usare le parti di verifica dell'API di debug, il debug in-process. Tuttavia, a causa di commenti e suggerimenti dei clienti, debug in-process è stati rimossi da .NET Framework versione 2.0 e sostituito con un set di funzionalità che è più in linea con l'API di profilatura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versione di .NET framework:** 1.0  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
