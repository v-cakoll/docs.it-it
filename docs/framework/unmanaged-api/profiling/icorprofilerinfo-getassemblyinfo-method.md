---
title: Metodo ICorProfilerInfo::GetAssemblyInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAssemblyInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- GetAssemblyInfo Method
helpviewer_keywords:
- GetAssemblyInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetAssemblyInfo method [.NET Framework profiling]
ms.assetid: 7a3c97c3-1e31-47b1-bf23-386785c509c4
topic_type:
- apiref
ms.openlocfilehash: 41083b2fcd61a9a726e835c3d5710308aa634600
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84498635"
---
# <a name="icorprofilerinfogetassemblyinfo-method"></a>Metodo ICorProfilerInfo::GetAssemblyInfo
Accetta l'ID di un assembly e restituisce il nome dell'assembly e l'ID del relativo modulo del manifesto.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAssemblyInfo(  
    [in]  AssemblyID  assemblyId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] AppDomainID *pAppDomainId,  
    [out] ModuleID    *pModuleId);  
```  
  
## <a name="parameters"></a>Parametri  
 `assemblyId`  
 [in] Identificatore dell'assembly.  
  
 `cchName`  
 [in] Lunghezza del parametro `szName` in caratteri.  
  
 `pcchName`  
 [out] Puntatore ai caratteri totali del nome dell'assembly.  
  
 `szName`  
 [out] Buffer per caratteri di tipo "wide" fornito dal chiamante. Una volta completata, la funzione conterrà il nome dell'assembly.  
  
 `pAppDomainId`  
 [out] Puntatore all'ID del dominio dell'applicazione che contiene l'assembly.  
  
 `pModuleId`  
 [out] Puntatore all'ID del modulo del manifesto dell'assembly.  
  
## <a name="remarks"></a>Osservazioni  
 Quando il metodo viene completato, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome completo dell'assembly. A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`. Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetAssemblyInfo`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetAssemblyInfo` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito in `pcchName` e chiamare nuovamente `GetAssemblyInfo`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](icorprofilerinfo-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
