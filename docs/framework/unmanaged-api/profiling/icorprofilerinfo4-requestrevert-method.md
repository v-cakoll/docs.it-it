---
title: Metodo ICorProfilerInfo4::RequestRevert
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.RequestRevert
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::RequestRevert
helpviewer_keywords:
- RequestRevert method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::RequestRevert method [.NET Framework profiling]
ms.assetid: 70261da5-5933-4e25-9de0-ddf51cba56cc
topic_type:
- apiref
ms.openlocfilehash: 73d122b1ffa890bfa43f8eef7e24595ac0d26ebe
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861788"
---
# <a name="icorprofilerinfo4requestrevert-method"></a>Metodo ICorProfilerInfo4::RequestRevert
Ripristina tutte le istanze delle funzioni specificate alle versioni originali.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT RequestRevert (  
   [in] ULONG    cFunctions,  
   [in, size_is(cFunctions)]  ModuleID    moduleIds[],  
   [in, size_is(cFunctions)]  mdMethodDef methodIds[],  
   [out, size_is(cFunctions)]  HRESULT status[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `cFunctions`  
 [in] Numero delle funzioni da ripristinare.  
  
 `moduleIds`  
 [in] Specifica la parte `moduleId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ripristinare.  
  
 `methodIds`  
 [in] Specifica la parte `methodId` delle coppie (`module`, `methodDef`) che identificano le funzioni da ripristinare.  
  
 `status`  
 [out] Matrice di HRESULT riportati nella sezione "HRESULT di stato" più avanti in questo argomento. Ciascun HRESULT indica la riuscita o la mancata riuscita del ripristino di ogni funzione specificata nelle matrici `moduleIds` e `methodIds` parallele.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.  
  
|HRESULT|Descrizione|  
|-------------|-----------------|  
|S_OK|È stato effettuato un tentativo di ripristinare tutte le richieste. Tuttavia, la matrice di stato restituito deve essere verificata per determinare quali funzioni sono state annullate correttamente.|  
|CORPROF_E_CALLBACK4_REQUIRED|Il profiler deve implementare l'interfaccia [ICorProfilerCallback4](icorprofilercallback4-interface.md) per il supporto di questa chiamata.|  
|CORPROF_E_REJIT_NOT_ENABLED|La ricompilazione JIT non è stata abilitata. È necessario abilitare la ricompilazione JIT durante l'inizializzazione usando il metodo [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) per impostare il flag di `COR_PRF_ENABLE_REJIT`.|  
|E_INVALIDARG|Il parametro `cFunctions` è pari a 0 oppure `moduleIds` o `methodIds` è `NULL`.|  
|E_OUTOFMEMORY|CLR non è stato in grado di completare la richiesta a causa di memoria insufficiente.|  
  
## <a name="status-hresults"></a>HRESULT di stato  
  
|HRESULT matrice di stato|Descrizione|  
|--------------------------|-----------------|  
|S_OK|La funzione corrispondente è stata ripristinata.|  
|E_INVALIDARG|Il parametro `moduleID` o il parametro `methodDef` è `NULL`.|  
|CORPROF_E_DATAINCOMPLETE|Il modulo non è ancora completamente caricato o è in fase di scaricamento.|  
|CORPROF_E_MODULE_IS_DYNAMIC|Il modulo specificato è stato generato dinamicamente (ad esempio da `Reflection.Emit`). Di conseguenza, non è supportato da questo metodo.|  
|CORPROF_E_ACTIVE_REJIT_REQUEST_NOT_FOUND|CLR non può ripristinare la funzione specificata, perché non è stata trovata una richiesta di ricompilazione attiva corrispondente. La ricompilazione non è stata mai richiesta oppure la funzione era già stata ripristinata.|  
|Altro|Il sistema operativo ha restituito un errore esterno al controllo di CLR. Ad esempio, se una chiamata al sistema per modificare la sicurezza di accesso di una pagina di memoria non riesce, viene visualizzato un errore del sistema operativo.|  
  
## <a name="remarks"></a>Note  
 La volta successiva che verranno chiamate tutte le istanze di funzione ripristinate, verranno eseguite le versioni originali delle funzioni. Se una funzione è già in esecuzione, verrà terminata l'esecuzione della versione in esecuzione.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo4](icorprofilerinfo4-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
