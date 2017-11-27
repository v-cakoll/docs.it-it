---
title: Metodo ICorProfilerInfo::IsArrayClass
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.IsArrayClass
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: cd07541095158d17b80333b83015d6b1f33a5dcc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoisarrayclass-method"></a>Metodo ICorProfilerInfo::IsArrayClass
Determina se la classe specificata è una classe della matrice.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classId`  
 [in] L'ID della classe da esaminare.  
  
 `pBaseElemType`  
 [out] Un puntatore a un valore dell'enumerazione CorElementType che indica il tipo degli elementi della matrice.  
  
 `pBaseClassId`  
 [out] Un puntatore all'ID classe degli elementi della matrice, se disponibile.  
  
 `pcRank`  
 [out] Un puntatore a un intero che indica il rango (numero di dimensioni) della matrice.  
  
## <a name="remarks"></a>Note  
 Se la classe specificata è una classe della matrice, il `IsArrayClass` metodo restituisce un HRESULT S_OK e i valori per i parametri di output non null. In caso contrario, restituisce S_FALSE.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
