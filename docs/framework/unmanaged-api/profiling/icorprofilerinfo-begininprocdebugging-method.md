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
ms.openlocfilehash: fffc028c7706c86e8384483cc92ebad90b292861
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447745"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a>Metodo ICorProfilerInfo::BeginInprocDebugging
Inizializza il supporto per il debug in-process. Questo metodo è obsoleto nella versione .NET Framework 2,0.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a>Parametri  
 `fThisThreadOnly`  
 in Impostare questo valore su `true` per inizializzare il supporto del debug solo per il thread corrente. impostarlo su `false` per inizializzare il supporto del debug per tutti i thread.  
  
 `pdwProfilerContext`  
 out Puntatore a un valore restituito che identifica la sessione di debug.  
  
## <a name="remarks"></a>Note  
 I servizi di debug CLR supportano il debug in-process limitato nelle versioni .NET Framework 1,0 e 1,1. Il debug in-process ha consentito a un profiler di usare le parti di ispezione dell'API di debug. Tuttavia, a causa dei suggerimenti dei clienti, il debug in-process è stato rimosso dalla .NET Framework nella versione 2,0 e sostituito con un set di funzionalità più in linea con l'API di profilatura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versione .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
