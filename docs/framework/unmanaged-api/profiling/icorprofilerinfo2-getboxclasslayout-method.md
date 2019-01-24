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
ms.openlocfilehash: b9d775d5c386abeb100604250008ebf1bf377e8b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54550812"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>Metodo ICorProfilerInfo2::GetBoxClassLayout
Ottiene informazioni su dove si trova il tipo di valore specificato quando è sottoposto a boxing.  
  
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
 [out] Valore intero che rappresenta l'offset, relativo al puntatore, ID di oggetto boxed del tipo di valore.  
  
## <a name="remarks"></a>Note  
 Il `pBufferOffset` valore rappresenta il percorso del tipo di valore all'interno di una finestra. Dopo aver `pBufferOffset` viene applicato a un oggetto sottoposto a conversione boxing, layout di classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
