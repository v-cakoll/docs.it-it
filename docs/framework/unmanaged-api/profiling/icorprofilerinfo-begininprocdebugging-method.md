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
ms.openlocfilehash: c14979fa711145b9f1a134f90d7450b24e6d8a15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76864297"
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
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versione .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
