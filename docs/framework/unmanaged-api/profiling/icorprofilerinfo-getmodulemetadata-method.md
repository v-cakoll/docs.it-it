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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2e63cf698e41e70084c9b71bdf58d7ac60723d53
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782782"
---
# <a name="icorprofilerinfogetmodulemetadata-method"></a>Metodo ICorProfilerInfo::GetModuleMetaData
Ottiene un'istanza di interfaccia di metadati che esegue il mapping per il modulo specificato.  
  
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
 [in] L'ID del modulo a cui verrà mappato l'istanza dell'interfaccia.  
  
 `dwOpenFlags`  
 [in] Valore di [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumerazione che specifica la modalità di apertura dei file manifesto. Solo le `ofRead`, `ofWrite` e `ofNoTransform` bits sono validi.  
  
 `riid`  
 [in] Il riferimento all'ID (GUID) dell'interfaccia di metadati la cui istanza verrà recuperato. Visualizzare [interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md) per un elenco delle interfacce.  
  
 `ppOut`  
 [out] Un puntatore all'indirizzo dell'istanza di interfaccia di metadati.  
  
## <a name="remarks"></a>Note  
 È possibile richiedere i metadati da aprire in modalità lettura/scrittura, ma ciò comporterà rallenterà l'esecuzione del programma, perché le modifiche apportate per i metadati non possono essere ottimizzato come avveniva dal compilatore.  
  
 Alcuni moduli (ad esempio, i moduli delle risorse) non hanno metadati. In questi casi `GetModuleMetaData` restituirà un valore HRESULT di S_FALSE e un valore null in *`ppOut`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
