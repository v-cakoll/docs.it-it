---
title: Metodo ICorProfilerInfo::GetModuleMetaData
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleMetaData
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleMetaData
helpviewer_keywords:
- GetModuleMetaData method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleMetaData method [.NET Framework profiling]
ms.assetid: 7a439d92-348a-44dd-b60f-cad7cba56379
topic_type:
- apiref
ms.openlocfilehash: c7bf8e3ebedb17a4536b604909434c3e004fc828
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439836"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>Metodo ICorProfilerInfo::GetModuleMetaData
Ottiene un'istanza dell'interfaccia di metadati mappata al modulo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetModuleMetaData(  
    [in]  ModuleID moduleId,  
    [in]  DWORD    dwOpenFlags,  
    [in]  REFIID   riid,  
    [out] IUnknown **ppOut);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 in ID del modulo a cui verrà eseguito il mapping dell'istanza dell'interfaccia.  
  
 `dwOpenFlags`  
 in Valore dell'enumerazione [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) che specifica la modalità di apertura dei file manifesto. Sono validi solo i bit `ofRead`, `ofWrite` e `ofNoTransform`.  
  
 `riid`  
 in ID di riferimento (GUID) dell'interfaccia di metadati di cui verrà recuperata l'istanza. Per un elenco delle interfacce, vedere [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) .  
  
 `ppOut`  
 out Puntatore all'indirizzo dell'istanza dell'interfaccia dei metadati.  
  
## <a name="remarks"></a>Note  
 È possibile richiedere l'apertura dei metadati in modalità di lettura/scrittura, ma ciò comporterà un'esecuzione più lenta dei metadati del programma, perché le modifiche apportate ai metadati non possono essere ottimizzate così come sono state dal compilatore.  
  
 Alcuni moduli, ad esempio i moduli di risorse, non dispongono di metadati. In questi casi, `GetModuleMetaData` restituirà un valore HRESULT di S_FALSE e un valore null in *`ppOut`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
