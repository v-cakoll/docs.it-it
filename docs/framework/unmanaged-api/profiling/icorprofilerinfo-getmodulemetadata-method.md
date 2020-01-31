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
ms.openlocfilehash: 6e787de6287dc5b3091d3671d3da2f2154b12e88
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76869924"
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
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
