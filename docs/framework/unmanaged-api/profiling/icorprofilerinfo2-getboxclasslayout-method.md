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
ms.openlocfilehash: 5f98c35f77fdb200be2e96364c9ac06c386faa62
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436016"
---
# <a name="icorprofilerinfo2getboxclasslayout-method"></a>Metodo ICorProfilerInfo2::GetBoxClassLayout
Ottiene informazioni sul punto in cui si trova il tipo di valore specificato quando viene sottoposto a Boxing.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetBoxClassLayout(  
    [in] ClassID classId,  
    [out] ULONG32 *pBufferOffset);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 in ID della classe che descrive il tipo di valore boxed.  
  
 `pBufferOffset`  
 out Intero che rappresenta l'offset, relativo al puntatore ID oggetto boxed, del tipo di valore.  
  
## <a name="remarks"></a>Osservazioni  
 Il valore `pBufferOffset` è il percorso del tipo di valore all'interno di una casella. Dopo l'applicazione di `pBufferOffset` a un oggetto boxed, il layout della classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
