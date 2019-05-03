---
title: Metodo ICorProfilerInfo2::GetCodeInfo2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetCodeInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetCodeInfo2
helpviewer_keywords:
- ICorProfilerInfo2::GetCodeInfo2 method [.NET Framework profiling]
- GetCodeInfo2 method [.NET Framework profiling]
ms.assetid: 532da6ee-7f0a-401b-a61e-fc47ec235d2e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1acf77c250b47bb32a83227a427dd3fe4f909a33
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62041023"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a>Metodo ICorProfilerInfo2::GetCodeInfo2
Ottiene gli ambiti del codice nativo associato al parametro `FunctionID` specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCodeInfo2(  
    [in]  FunctionID functionID,  
    [in]  ULONG32 cCodeInfos,  
    [out] ULONG32 *pcCodeInfos,  
    [out, size_is(cCodeInfos), length_is(*pcCodeInfos)]  
    COR_PRF_CODE_INFO codeInfos[]);  
```  
  
## <a name="parameters"></a>Parametri  
 `functionID`  
 [in] ID della funzione alla quale è associato il codice nativo.  
  
 `cCodeInfos`  
 [in] Dimensione della matrice `codeInfos`.  
  
 `pcCodeInfos`  
 [out] Un puntatore al numero totale di [COR_PRF_CODE_INFO](../../../../docs/framework/unmanaged-api/profiling/cor-prf-code-info-structure.md) strutture disponibili.  
  
 `codeInfos`  
 [out] Buffer fornito dal chiamante. Una volta completato, il metodo contiene una matrice di strutture `COR_PRF_CODE_INFO`, ognuna delle quali descrive un blocco di codice nativo.  
  
## <a name="remarks"></a>Note  
 Gli ambiti vengono ordinati in sequenza crescente in base all'offset MSIL (Microsoft Intermediate Language).  
  
 Dopo il completamento del metodo `GetCodeInfo2`, è necessario verificare che il buffer `codeInfos` sia abbastanza grande per contenere tutte le strutture `COR_PRF_CODE_INFO`. A tale scopo, confrontare il valore di `cCodeInfos` con il valore del parametro `cchName`. Se il valore `cCodeInfos`, diviso per la dimensione di una struttura `COR_PRF_CODE_INFO`, è inferiore a `pcCodeInfos`, allocare un buffer `codeInfos` più grande, aggiornare `cCodeInfos` con la nuova dimensione e chiamare nuovamente `GetCodeInfo2`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetCodeInfo2` con un buffer `codeInfos` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer `codeInfos` sul valore restituito in `pcCodeInfos` moltiplicato per la dimensione di una struttura `COR_PRF_CODE_INFO` e chiamare di nuovo `GetCodeInfo2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetCodeInfo3](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-getcodeinfo3-method.md)
- [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
- [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
