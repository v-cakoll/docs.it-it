---
title: Metodo ICorProfilerInfo::GetAppDomainInfo
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetAppDomainInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetAppDomainInfo
helpviewer_keywords:
- ICorProfilerInfo::GetAppDomainInfo method [.NET Framework profiling]
- GetAppDomainInfo method [.NET Framework profiling]
ms.assetid: a6bf5a04-e03e-44f0-917a-96f6a6d3cc96
topic_type:
- apiref
ms.openlocfilehash: 8c13ce443037d706f9eba49760ba76f47c5a6538
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448181"
---
# <a name="icorprofilerinfogetappdomaininfo-method"></a>Metodo ICorProfilerInfo::GetAppDomainInfo
Accetta un ID del dominio dell'applicazione. Restituisce il nome di un domino applicazione e l'ID del processo che lo contiene.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAppDomainInfo(  
    [in]  AppDomainID appDomainId,  
    [in]  ULONG       cchName,  
    [out] ULONG       *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)]  
          WCHAR       szName[] ,  
    [out] ProcessID   *pProcessId);  
```  
  
## <a name="parameters"></a>Parametri  
 `appDomainId`  
 [in] ID del dominio dell'applicazione.  
  
 `cchName`  
 [in] Lunghezza, espressa in caratteri, del buffer restituito `szName`.  
  
 `pcchName`  
 [out] Puntatore ai caratteri totali del nome del dominio dell'applicazione.  
  
 `szName`  
 [out] Buffer per caratteri di tipo "wide" fornito dal chiamante. Una volta completato il metodo, il parametro `szName` conterrà il nome del dominio dell'applicazione completo o parziale.  
  
 `pProcessId`  
 [out] Puntatore all'ID del processo che contiene il dominio dell'applicazione.  
  
## <a name="remarks"></a>Note  
 Dopo il completamento del metodo, è necessario verificare che il buffer `szName` sia abbastanza grande per contenere il nome completo del dominio dell'applicazione. A tale scopo, confrontare il valore a cui punta `pcchName` con il valore del parametro `cchName`. Se `pcchName` punta a un valore maggiore di `cchName`, allocare un buffer `szName` più grande, aggiornare `cchName` con la nuova dimensione e chiamare nuovamente `GetAppDomainInfo`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetAppDomainInfo` con un buffer `szName` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcchName` e chiamare nuovamente `GetAppDomainInfo`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
