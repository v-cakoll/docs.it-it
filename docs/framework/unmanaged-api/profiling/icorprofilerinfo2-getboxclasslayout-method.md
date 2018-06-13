---
title: Metodo ICorProfilerInfo2::GetBoxClassLayout
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetBoxClassLayout
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetBoxClassLayout
helpviewer_keywords:
- GetBoxClassLayout method [.NET Framework profiling]
- ICorProfilerInfo2::GetBoxClassLayout method [.NET Framework profiling]
ms.assetid: 624672b5-1189-488a-85d2-3e12b49617c1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f046fb51753bfa79d333d465e8850794ecc73973
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453538"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>Metodo ICorProfilerInfo2::GetBoxClassLayout
Ottiene informazioni sul tipo di valore specificato in cui si trova quando viene sottoposto a boxing.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
#### <a name="parameters"></a>Parametri  
 `classId`  
 [in] L'ID della classe che descrive il tipo di valore boxed.  
  
 `pBufferOffset`  
 [out] Valore intero che rappresenta l'offset, rispetto al puntatore all'ID dell'oggetto di tipo boxed, del tipo di valore.  
  
## <a name="remarks"></a>Note  
 Il `pBufferOffset` valore rappresenta il percorso del tipo di valore all'interno di una casella. Dopo aver `pBufferOffset` viene applicato a un oggetto boxed, layout della classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
