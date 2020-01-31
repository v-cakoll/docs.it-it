---
title: Metodo ICorProfilerInfo2::GetStaticFieldInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetStaticFieldInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type:
- apiref
ms.openlocfilehash: d30d0bc262d76cf8980f90d8384173d89baf92d5
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862685"
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a>Metodo ICorProfilerInfo2::GetStaticFieldInfo
Ottiene un valore che indica il tipo di statico che si applica al campo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 in ID della classe in cui è definito il campo statico.  
  
 `fieldToken`  
 in Token di metadati per il campo statico.  
  
 `pFieldInfo`  
 out Puntatore a un valore dell'enumerazione [COR_PRF_STATIC_TYPE](cor-prf-static-type-enumeration.md) che indica se il campo specificato è statico e, in tal caso, il tipo di statico applicato al campo.  
  
## <a name="remarks"></a>Note  
 Queste informazioni possono essere usate per determinare la funzione da chiamare per ottenere l'indirizzo del campo statico.  
  
 Il codice del profiler dovrebbe ancora verificare i metadati per un campo statico per assicurarsi che disponga effettivamente di un indirizzo. I valori letterali statici, ovvero le costanti, esistono solo nei metadati e non hanno un indirizzo.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
