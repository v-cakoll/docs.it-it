---
title: Metodo ICorProfilerInfo2::GetAppDomainStaticAddress
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetAppDomainStaticAddress
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress
helpviewer_keywords:
- ICorProfilerInfo2::GetAppDomainStaticAddress method [.NET Framework profiling]
- GetAppDomainStaticAddress method [.NET Framework profiling]
ms.assetid: 2a9e0ea7-a9e2-4817-b1c4-fcf15b215ea9
topic_type:
- apiref
ms.openlocfilehash: 05d8c44655d8670194035c336bd62ae5d53bfec3
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862971"
---
# <a name="icorprofilerinfo2getappdomainstaticaddress-method"></a>Metodo ICorProfilerInfo2::GetAppDomainStaticAddress
Ottiene l'indirizzo del campo statico del dominio dell'applicazione specificato nell'ambito del dominio dell'applicazione specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
RESULT GetAppDomainStaticAddress(  
    [in] ClassID classId,  
    [in] mdFieldDef fieldToken,  
    [in] AppDomainID appDomainId,  
    [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 in ID classe della classe che contiene il campo statico dell'applicazione richiesto.  
  
 `fieldToken`  
 in Token di metadati per il campo di dominio applicazione richiesto-statico.  
  
 `appDomainId`  
 in ID del dominio applicazione che rappresenta l'ambito per il campo statico richiesto.  
  
 `ppAddress`  
 out Puntatore all'indirizzo del campo statico che si trova all'interno del dominio applicazione specificato.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetAppDomainStaticAddress` può restituire uno dei seguenti elementi:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.  
  
- Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection. Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.  
  
 Prima che il costruttore della classe di una classe venga completato, `GetAppDomainStaticAddress` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e vengono radicati Garbage Collection oggetti.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
