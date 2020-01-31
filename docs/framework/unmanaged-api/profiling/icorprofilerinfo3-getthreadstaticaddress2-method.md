---
title: Metodo ICorProfilerInfo3::GetThreadStaticAddress2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetThreadStaticAddress2 Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2
helpviewer_keywords:
- ICorProfilerInfo3::GetThreadStaticAddress2 method [.NET Framework profiling]
- GetThreadStaticAddress2 method [.NET Framework profiling]
ms.assetid: a9608861-ae64-4467-8a73-be05ad34beac
topic_type:
- apiref
ms.openlocfilehash: 5ebd1f2780ab25e01bcb384b38220f414d90292e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868538"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a>Metodo ICorProfilerInfo3::GetThreadStaticAddress2
Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del dominio dell'applicazione e del thread specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 in ID della classe che contiene il campo statico di thread richiesto.  
  
 `fieldToken`  
 in Token di metadati per il campo statico di thread richiesto.  
  
 `appDomainId`  
 [in] ID del dominio dell'applicazione.  
  
 `threadId`  
 in ID del thread che rappresenta l'ambito per il campo statico richiesto.  
  
 `ppAddress`  
 out Puntatore all'indirizzo del campo statico che si trova all'interno del thread specificato.  
  
## <a name="remarks"></a>Note  
 Il metodo `GetThreadStaticAddress2` può restituire uno dei seguenti elementi:  
  
- CORPROF_E_DATAINCOMPLETE HRESULT se al campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.  
  
- Indirizzi degli oggetti che possono trovarsi nell'heap Garbage Collection. Questi indirizzi potrebbero non essere più validi dopo Garbage Collection, quindi, dopo Garbage Collection, i profiler non devono presupporre che siano validi.  
  
 Prima che il costruttore della classe di una classe venga completato, `GetThreadStaticAddress2` restituirà CORPROF_E_DATAINCOMPLETE per tutti i campi statici, anche se alcuni dei campi statici potrebbero essere già inizializzati e vengono radicati Garbage Collection oggetti.  
  
 Il metodo [ICorProfilerInfo2:: GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md) è simile al metodo `GetThreadStaticAddress2`, ma non accetta un argomento del dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo3](icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
