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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7fe86fbe7ee51e5f53eeea74d7d5a56046de5e00
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57484394"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a>Metodo ICorProfilerInfo2::GetArrayObjectInfo
Ottiene informazioni dettagliate su un oggetto matrice.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID di un oggetto matrice valida.  
  
 `cDimensions`  
 [in] La classificazione (numero di dimensioni) della matrice.  
  
 `pDimensionSizes`  
 [out] Matrice che contiene numeri interi, ognuno dei quali rappresenta la dimensione di una dimensione della matrice.  
  
 `pDimensionLowerBounds`  
 [out] Matrice che contiene numeri interi, ognuno dei quali rappresenta minore associato di una dimensione della matrice.  
  
 `ppData`  
 [out] Un puntatore all'indirizzo del buffer non elaborato per la matrice, di cui viene disposta seguendo la convenzione di C++.  
  
## <a name="remarks"></a>Note  
 Il `pDimensionSizes` e `pDimensionLowerBounds` sono matrici parallele, in modo che gli elementi che si trova in corrispondenza dell'indice stesso in ogni matrice sono illustrate le caratteristiche della stessa entità.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
