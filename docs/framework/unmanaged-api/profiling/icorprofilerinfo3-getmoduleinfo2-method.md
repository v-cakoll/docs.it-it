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
ms.openlocfilehash: 96cde35c7151bb7ce58715f2826feaa59b30efab
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862308"
---
# <a name="icorprofilerinfo3getmoduleinfo2-method"></a>Metodo ICorProfilerInfo3::GetModuleInfo2
Dato un ID modulo, restituisce il nome file del modulo, l'ID dell'assembly padre del modulo e una maschera di bit che descrive le proprietà del modulo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
 `pdwModuleFlags`  
 out Maschera di maschera dei valori dell'enumerazione [COR_PRF_MODULE_FLAGS](cor-prf-module-flags-enumeration.md) che specificano le proprietà del modulo.  
  
## <a name="remarks"></a>Note  
 Per i moduli dinamici, il parametro `szName` è il nome di metadati del modulo e l'indirizzo di base è 0 (zero). Il nome dei metadati è il valore nella colonna Name dalla tabella Module all'interno dei metadati. Viene anche esposto come proprietà <xref:System.Reflection.Module.ScopeName%2A?displayProperty=nameWithType> al codice gestito e come parametro di `szName` del metodo [IMetaDataImport:: GetScopeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md) al codice client dei metadati non gestiti.  
  
 Sebbene il metodo `GetModuleInfo2` possa essere chiamato non appena l'ID del modulo esiste, l'ID dell'assembly padre non sarà disponibile fino a quando il profiler non riceve il callback [ICorProfilerCallback:: ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md) .  
  
 Dopo il completamento del metodo `GetModuleInfo2`, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome file completo del modulo. A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`. Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetModuleInfo2`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetModuleInfo2` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcchName` e chiamare nuovamente `GetModuleInfo2`.  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
