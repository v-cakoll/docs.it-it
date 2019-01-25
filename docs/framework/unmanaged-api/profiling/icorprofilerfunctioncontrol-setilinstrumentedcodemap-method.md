---
title: Metodo ICorProfilerFunctionControl::SetILInstrumentedCodeMap
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionControl.SetILInstrumentedCodeMap
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap
helpviewer_keywords:
- ICorProfilerFunctionControl::SetILInstrumentedCodeMap method [.NET Framework profiling]
- SetIILInstrumentedCodeMap method, ICorProfilerFunctionControl interface [.NET Framework profiling]
ms.assetid: ecf56646-7e5f-46c4-8340-f3a04e88920f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81880f5f97d1c8f16c80f3e3cb2a1be506d44e2d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54571035"
---
# <a name="icorprofilerfunctioncontrolsetilinstrumentedcodemap-method"></a>Metodo ICorProfilerFunctionControl::SetILInstrumentedCodeMap
Imposta una mappa del codice per la funzione specificata usando le voci della mappa CIL (Common Intermediate Language) specificate.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetILInstrumentedCodeMap(  
    [in]   ULONG      cILMapEntries,  
    [in, size_is(cILMapEntries)] COR_IL_MAP rgILMapEntries[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `cILMapEntries`  
 [in] Numero di voci nella mappa.  
  
 `rgILMapEntries`  
 [in] Matrice allocata dal chiamante di voci COR_IL_MAP. L'interpretazione di queste voci è uguali a quelle per il [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) (metodo).  
  
## <a name="remarks"></a>Note  
 Imposta il mapping chiamando questo metodo consente al debugger di recuperare il mapping chiamando [ICorDebugILCode2::GetInstrumentedILMap](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-getinstrumentedilmap-method.md). Il debugger potrà anche usare il mapping internamente durante il calcolo degli offset IL per le analisi dello stack e la durata delle variabili.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
