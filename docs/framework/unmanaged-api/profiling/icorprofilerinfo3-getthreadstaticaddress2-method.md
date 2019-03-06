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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 49139f5b1f65bc2e258362d9b47f4e0d44cc6894
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481521"
---
# <a name="icorprofilerinfo3getthreadstaticaddress2-method"></a>Metodo ICorProfilerInfo3::GetThreadStaticAddress2
Ottiene l'indirizzo del campo statico a livello di thread specificato che è nell'ambito del dominio dell'applicazione e del thread specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetThreadStaticAddress2(  
                [in] ClassID classId,  
                [in] mdFieldDef fieldToken,  
                [in] AppDomainID appDomainId,  
                [in] ThreadID threadId,  
                [out] void **ppAddress);  
```  
  
## <a name="parameters"></a>Parametri  
 `classId`  
 [in] L'ID della classe che contiene il campo statico thread richiesto.  
  
 `fieldToken`  
 [in] Il token di metadati per il campo statico thread richiesto.  
  
 `appDomainId`  
 [in] ID del dominio dell'applicazione.  
  
 `threadId`  
 [in] L'ID del thread che è l'ambito per i campi statici richiesti.  
  
 `ppAddress`  
 [out] Un puntatore all'indirizzo del campo statico che si trova all'interno del thread specificato.  
  
## <a name="remarks"></a>Note  
 Il `GetThreadStaticAddress2` metodo può restituire uno dei seguenti:  
  
-   Un valore HRESULT CORPROF_E_DATAINCOMPLETE se il campo statico specificato non è stato assegnato un indirizzo nel contesto specificato.  
  
-   Gli indirizzi di oggetti che possono trovarsi nell'heap di garbage collection. Questi indirizzi potrebbero diventare non validi dopo l'operazione di garbage collection, in modo che dopo l'operazione di garbage collection, i profiler non devono presupporre che siano validi.  
  
 Prima del completamento, il costruttore di classe della classe `GetThreadStaticAddress2` restituirà CORPROF_E_DATAINCOMPLETE per tutti i relativi campi statici, anche se alcuni dei campi statici potrebbero essere già stato inizializzato e oggetti radice del garbage collection.  
  
 Il [ICorProfilerInfo2::GetThreadStaticAddress](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md) metodo è simile al `GetThreadStaticAddress2` (metodo), ma non accetta un argomento di dominio dell'applicazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
