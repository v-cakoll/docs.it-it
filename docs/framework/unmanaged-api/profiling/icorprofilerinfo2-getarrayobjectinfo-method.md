---
title: Metodo ICorProfilerInfo2::GetArrayObjectInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetArrayObjectInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b20530081f7c9ad32f4702099abacc78e052ebd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
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
  
#### <a name="parameters"></a>Parametri  
 `objectId`  
 [in] L'ID di un oggetto matrice valida.  
  
 `cDimensions`  
 [in] La classificazione (numero di dimensioni) della matrice.  
  
 `pDimensionSizes`  
 [out] Matrice che contiene numeri interi, ognuno dei quali rappresenta la dimensione di una dimensione della matrice.  
  
 `pDimensionLowerBounds`  
 [out] Una matrice che contiene numeri interi, ognuno dei quali rappresenta inferiore associato di una dimensione della matrice.  
  
 `ppData`  
 [out] Un puntatore all'indirizzo del buffer non elaborato per la matrice, che è disposto in base alla convenzione di C++.  
  
## <a name="remarks"></a>Note  
 Il `pDimensionSizes` e `pDimensionLowerBounds` sono matrici parallele, pertanto gli elementi in corrispondenza dell'indice stesso in ogni matrice sono caratteristiche della stessa entità.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
