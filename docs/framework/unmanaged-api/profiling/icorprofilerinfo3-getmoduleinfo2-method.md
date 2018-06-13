---
title: Metodo ICorProfilerInfo3::GetModuleInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetModuleInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetModuleInfo2
helpviewer_keywords:
- ICorProfilerInfo3::GetModuleInfo2 method [.NET Framework profiling]
- GetModuleInfo2 method [.NET Framework profiling]
ms.assetid: f1f6b8f3-dcfc-49e8-be76-ea50ea90d5a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d461f5dc85c7107e36fc1492ac88f37d42ba9f24
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459466"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a>Metodo ICorProfilerInfo3::GetModuleInfo2
Dato un ID modulo, restituisce il nome file del modulo, l'ID dell'assembly padre del modulo e una maschera di bit che descrive le proprietà del modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetModuleInfo2(  
    [in]  ModuleID   moduleId,  
    [out] LPCBYTE    *ppBaseLoadAddress,  
    [in]  ULONG      cchName,  
    [out] ULONG      *pcchName,  
    [out, annotation("__out_ecount_part(cchName, *pcchName)")]  
          WCHAR      szName[] ,  
    [out] AssemblyID *pAssemblyId);  
    [out] DWORD                 *pdwModuleFlags);  
```  
  
#### <a name="parameters"></a>Parametri  
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
  
 `pdwModuleFlags`  
 [out] Maschera di bit dei valori di [COR_PRF_MODULE_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-module-flags-enumeration.md) enumerazione che specificano le proprietà del modulo.  
  
## <a name="remarks"></a>Note  
 Per i moduli dinamici, il parametro `szName` è il nome di metadati del modulo e l'indirizzo di base è 0 (zero). Il nome dei metadati è il valore nella colonna Name dalla tabella Module all'interno dei metadati. È esposto anche come il <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> proprietà al codice gestito e come il `szName` parametro del [IMetaDataImport:: GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) metodo al codice client di metadati non gestite.  
  
 Sebbene il `GetModuleInfo2` metodo può essere chiamato non appena l'ID del modulo, l'ID dell'assembly padre non saranno disponibile fino a quando il profiler avrà ricevuto il [ICorProfilerCallback:: ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md) callback.  
  
 Dopo il completamento del metodo `GetModuleInfo2`, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome file completo del modulo. A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`. Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetModuleInfo2`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetModuleInfo2` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcchName` e chiamare nuovamente `GetModuleInfo2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
