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
ms.openlocfilehash: 8160bb5b9ca5e0a4e22a1a831e978eaf125e7605
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76870492"
---
# <a name="icorprofilerinfogetilfunctionbody-method"></a>Metodo ICorProfilerInfo::GetILFunctionBody
Ottiene un puntatore al corpo di un metodo nel codice MSIL (Microsoft Intermediate Language), a partire dalla relativa intestazione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetILFunctionBody(  
    [in]  ModuleID    moduleId,  
    [in]  mdMethodDef methodId,  
    [out] LPCBYTE     *ppMethodHeader,  
    [out] ULONG       *pcbMethodSize);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 in ID del modulo in cui risiede la funzione.  
  
 `methodId`  
 in Token di metadati per il metodo.  
  
 `ppMethodHeader`  
 out Puntatore all'intestazione del metodo.  
  
 `pcbMethodSize`  
 out Integer che specifica le dimensioni del metodo.  
  
## <a name="remarks"></a>Note  
 Un metodo ha come ambito il modulo in cui risiede. Poiché il metodo `GetILFunctionBody` è progettato per concedere a uno strumento l'accesso al codice MSIL prima che sia stato caricato dal Common Language Runtime (CLR), usa il token di metadati del metodo per trovare l'istanza desiderata.  
  
 `GetILFunctionBody` possibile restituire un valore HRESULT CORPROF_E_FUNCTION_NOT_IL se il `methodId` punta a un metodo senza codice MSIL, ad esempio un metodo astratto o un metodo platform invoke (PInvoke).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
