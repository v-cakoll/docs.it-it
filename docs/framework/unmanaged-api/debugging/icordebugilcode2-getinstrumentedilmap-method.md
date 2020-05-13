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
ms.openlocfilehash: c6fdb7040620bb7a5b6aea6e0dc41e08d6f346d0
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210358"
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
 [in] Capacità di memoria della matrice `map`. Per ulteriori informazioni, vedere le sezione Note.  
  
 pcMap  
 [out] Numero di valori COR_IL_MAP scritti nella matrice map.  
  
 map  
 [out] Matrice di valori COR_IL_MAP che fornisce informazioni sui mapping dal linguaggio intermedio (IL) instrumentato dal profiler all'IL del metodo originale.  
  
## <a name="remarks"></a>Osservazioni  
 Se il profiler imposta il mapping chiamando il metodo [ICorProfilerInfo:: SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) , il debugger può chiamare questo metodo per recuperare il mapping e utilizzare il mapping internamente durante il calcolo degli offset il per le analisi dello stack e la durata delle variabili.  
  
 Se `cMap` è 0 e `pcMap` è diverso da**null**, `pcMap` viene impostato sul numero di valori di COR_IL_MAP disponibili. Se `cMap` è diverso da zero, rappresenta la capacità di memoria della matrice `map`. Quando il metodo viene restituito, `map` contiene un massimo di `cMap` elementi e `pcMap` viene impostato sul numero di COR_IL_MAP valori effettivamente scritti nella `map` matrice.  
  
 Se il linguaggio intermedio (IL) non è instrumentato o il profiler non ha fornito un mapping, il metodo restituisce `S_OK` e imposta `pcMap` su 0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorDebug.idl, CorDebug.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [ICorProfilerInfo::SetILInstrumentedCodeMap](../profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)
- [Interfaccia ICorDebugILCode2](icordebugilcode2-interface.md)
- [Interfacce di debug](debugging-interfaces.md)
