---
title: Metodo ICorDebugILCode2::GetInstrumentedILMap
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
ms.openlocfilehash: 7dede4e5af702f1b86b430450db4a669c326c062
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131069"
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>Metodo ICorDebugILCode2::GetInstrumentedILMap
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Restituisce una mappa dagli offset di linguaggio intermedio (IL) instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 cMap  
 [in] Capacità di memoria della matrice `map`. Per altre informazioni, vedere la sezione Osservazioni.  
  
 pcMap  
 out Numero di valori COR_IL_MAP scritti nella matrice della mappa.  
  
 map  
 out Matrice di valori COR_IL_MAP che forniscono informazioni sui mapping tra IL linguaggio IL del profiler e il il del metodo originale.  
  
## <a name="remarks"></a>Note  
 Se il profiler imposta il mapping chiamando il metodo [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , il debugger può chiamare questo metodo per recuperare il mapping e utilizzare il mapping internamente durante il calcolo degli offset il per le analisi dello stack e la variabile durata.  
  
 Se `cMap` è 0 e `pcMap` è diverso da**null**, `pcMap` viene impostato sul numero di valori COR_IL_MAP disponibili. Se `cMap` è diverso da zero, rappresenta la capacità di memoria della matrice `map`. Quando il metodo restituisce un risultato, `map` contiene un massimo di `cMap` elementi e `pcMap` è impostato sul numero di valori COR_IL_MAP effettivamente scritti nella matrice `map`.  
  
 Se il linguaggio intermedio (IL) non è instrumentato o il profiler non ha fornito un mapping, il metodo restituisce `S_OK` e imposta `pcMap` su 0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [Interfaccia ICorDebugILCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)
- [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
