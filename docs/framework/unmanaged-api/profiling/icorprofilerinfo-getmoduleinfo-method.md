---
title: Metodo ICorProfilerInfo::GetModuleInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetModuleInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetModuleInfo
helpviewer_keywords:
- GetModuleInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetModuleInfo method [.NET Framework profiling]
ms.assetid: 5a90d16f-7929-4987-8f83-a631becf564d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6cf4396de4eedf719f1f3fea0b9303a4eaed2bb6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467071"
---
# <a name="icorprofilerinfogetmoduleinfo-method"></a>Metodo ICorProfilerInfo::GetModuleInfo
Dato un ID modulo, restituisce il nome file del modulo e l'ID dell'assembly padre del modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetModuleInfo(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
```  
  
## <a name="parameters"></a>Parametri  
 `moduleId`  
 [in] ID del modulo per cui verranno recuperate informazioni.  
  
 `ppBaseLoadAddress`  
 [out] Indirizzo di base in cui viene caricato il modulo.  
  
 `cchName`  
 [in] Lunghezza, espressa in caratteri, del buffer restituito `szName`.  
  
 `pcchName`  
 [out] Puntatore alla lunghezza totale in caratteri del nome file del modulo che viene restituito.  
  
 `szName`  
 [out] Buffer per caratteri di tipo "wide" fornito dal chiamante. Quando il metodo viene completato, questo buffer contiene il nome file del modulo.  
  
 `pAssemblyId`  
 [out] Puntatore all'ID dell'assembly padre del modulo.  
  
## <a name="remarks"></a>Note  
 Per i moduli dinamici, il parametro `szName` è una stringa vuota e l'indirizzo di base è 0 (zero).  
  
 Anche se il `GetModuleInfo` metodo può essere chiamato, non appena l'ID del modulo esiste, l'ID dell'assembly padre non saranno disponibile fino a quando il profiler riceve le [ICorProfilerCallback:: ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.  
  
 Dopo il completamento del metodo `GetModuleInfo`, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome file completo del modulo. A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`. Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetModuleInfo`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetModuleInfo` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcchName` e chiamare nuovamente `GetModuleInfo`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
- [Metodo GetModuleInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)
