---
title: Metodo ICorProfilerInfo2::GetArrayObjectInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
ms.openlocfilehash: 839cd574e5352b74b47cd6242d5706bc6405d439
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862919"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>Metodo ICorProfilerInfo2::GetArrayObjectInfo
Ottiene informazioni dettagliate su un oggetto Array.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 in ID di un oggetto matrice valido.  
  
 `cDimensions`  
 in Rango (numero di dimensioni) della matrice.  
  
 `pDimensionSizes`  
 out Matrice contenente Integer, ognuno dei quali rappresenta la dimensione di una dimensione della matrice.  
  
 `pDimensionLowerBounds`  
 out Matrice contenente Integer, ognuno dei quali rappresenta il limite inferiore di una dimensione della matrice.  
  
 `ppData`  
 out Puntatore all'indirizzo del buffer non elaborato per la matrice, disposto in base alla C++ convenzione.  
  
## <a name="remarks"></a>Note  
 I `pDimensionSizes` e `pDimensionLowerBounds` sono matrici parallele, pertanto gli elementi che si trovano nello stesso indice in ogni matrice sono caratteristiche della stessa entità.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
