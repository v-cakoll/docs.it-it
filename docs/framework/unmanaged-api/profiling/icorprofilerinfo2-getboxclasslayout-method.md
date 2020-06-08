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
ms.openlocfilehash: 630b67a64716f26577bbc376970e4f76216f4da5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84497353"
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
 Il `pBufferOffset` valore è il percorso del tipo di valore all'interno di una casella. Dopo che `pBufferOffset` è stato applicato a un oggetto boxed, il layout della classe del tipo di valore può essere utilizzato per interpretare il valore dell'oggetto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
