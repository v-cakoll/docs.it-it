---
title: Metodo ICorProfilerInfo::GetILFunctionBody
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetILFunctionBody
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetILFunctionBody
helpviewer_keywords:
- GetILFunctionBody method [.NET Framework profiling]
- ICorProfilerInfo::GetILFunctionBody method [.NET Framework profiling]
ms.assetid: e29b46bc-5fdc-4894-b0c2-619df4b65ded
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a9e1ef61271e5b413972b8ba40a8fe8bac60ceeb
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54566214"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>Metodo ICorProfilerInfo::GetILFunctionBody
Ottiene un puntatore al corpo di un metodo in codice Microsoft intermediate language (MSIL), a partire dalla relativa intestazione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
#### <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] L'ID del modulo in cui risiede la funzione.  
  
 `methodId`  
 [in] Il token di metadati per il metodo.  
  
 `ppMethodHeader`  
 [out] Un puntatore all'intestazione del metodo.  
  
 `pcbMethodSize`  
 [out] Valore intero che specifica la dimensione del metodo.  
  
## <a name="remarks"></a>Note  
 L'ambito di un metodo è limitato dal modulo in cui si trovino. Poiché il `GetILFunctionBody` metodo è progettato per fornire l'accesso dello strumento per il codice MSIL prima che sia stato caricato da common language runtime (CLR), Usa il token di metadati del metodo per trovare l'istanza desiderata.  
  
 `GetILFunctionBody` può restituire un valore HRESULT CORPROF_E_FUNCTION_NOT_IL se il `methodId` punta a un metodo senza codice MSIL (ad esempio un metodo astratto, o un platform invoke (PInvoke) metodo).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
