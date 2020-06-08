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
ms.openlocfilehash: 62b34128be99ce7750d45e6c19e26bef7fcc98c5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502951"
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
 in Valore dell'enumerazione [CorOpenFlags](../metadata/coropenflags-enumeration.md) che specifica la modalità di apertura dei file manifesto. `ofRead` `ofWrite` Sono validi solo i `ofNoTransform` bit e.  
  
 `riid`  
 in ID di riferimento (GUID) dell'interfaccia di metadati di cui verrà recuperata l'istanza. Per un elenco delle interfacce, vedere [interfacce di metadati](../metadata/metadata-interfaces.md) .  
  
 `ppOut`  
 out Puntatore all'indirizzo dell'istanza dell'interfaccia dei metadati.  
  
## <a name="remarks"></a>Osservazioni  
 È possibile richiedere l'apertura dei metadati in modalità di lettura/scrittura, ma ciò comporterà un'esecuzione più lenta dei metadati del programma, perché le modifiche apportate ai metadati non possono essere ottimizzate così come sono state dal compilatore.  
  
 Alcuni moduli, ad esempio i moduli di risorse, non dispongono di metadati. In questi casi, `GetModuleMetaData` restituirà un valore HRESULT pari a S_FALSE e un valore null in * `ppOut` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
