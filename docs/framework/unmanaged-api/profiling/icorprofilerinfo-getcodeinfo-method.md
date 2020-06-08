---
title: Metodo ICorProfilerInfo::GetCodeInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetCodeInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetCodeInfo
helpviewer_keywords:
- GetCodeInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetCodeInfo method [.NET Framework profiling]
ms.assetid: 90140b0f-a926-4a7e-b6fa-23e05f703cce
topic_type:
- apiref
ms.openlocfilehash: eb6efc738b270f8f76d7130a12af4927fb6220ce
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498362"
---
# <a name="icorprofilerinfogetcodeinfo-method"></a>Metodo ICorProfilerInfo::GetCodeInfo
Ottiene l'ambito del codice nativo associato all'ID funzione specificato.  
  
 Questo metodo è obsoleto. Usare invece il metodo [ICorProfilerInfo2:: GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCodeInfo(  
    [in]  FunctionID functionId,  
    [out] LPCBYTE    *pStart,  
    [out] ULONG      *pcSize);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionId`  
 [in] ID della funzione alla quale è associato il codice nativo.  
  
 `pStart`  
 [out] Puntatore a una matrice di byte che costituiscono il codice nativo della funzione.  
  
 `pcSize`  
 [out] Puntatore a un intero che specifica la dimensione, in byte, del codice nativo.  
  
## <a name="remarks"></a>Osservazioni  
 Per ottimizzare le prestazioni, il runtime di .NET Framework versione 2.0 divide in più aree il codice nativo precompilato di una funzione. Il metodo `GetCodeInfo` pertanto è obsoleto in .NET Framework 2.0 perché non è in grado di gestire l'ambito del codice nativo di una funzione. I profiler devono invece iniziare a usare il metodo più generico `ICorProfilerInfo2::GetCodeInfo2`.  
  
 Questa funzione usa buffer allocati dal chiamante.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** 1,0  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
