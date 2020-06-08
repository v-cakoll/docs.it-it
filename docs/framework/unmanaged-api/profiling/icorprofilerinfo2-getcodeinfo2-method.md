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
ms.openlocfilehash: 04ce9ebded4be7ac3b20a4ceb78dd02294bbff4a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84502897"
---
# <a name="icorprofilerinfo2getcodeinfo2-method"></a>Metodo ICorProfilerInfo2::GetCodeInfo2
Ottiene gli ambiti del codice nativo associato al parametro `FunctionID` specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 out Puntatore al numero totale di strutture di [COR_PRF_CODE_INFO](cor-prf-code-info-structure.md) disponibili.  
  
 `codeInfos`  
 [out] Buffer fornito dal chiamante. Una volta completato, il metodo contiene una matrice di strutture `COR_PRF_CODE_INFO`, ognuna delle quali descrive un blocco di codice nativo.  
  
## <a name="remarks"></a>Osservazioni  
 Gli ambiti vengono ordinati in sequenza crescente in base all'offset MSIL (Microsoft Intermediate Language).  
  
 Dopo il completamento del metodo `GetCodeInfo2`, è necessario verificare che il buffer `codeInfos` sia abbastanza grande per contenere tutte le strutture `COR_PRF_CODE_INFO`. A tale scopo, confrontare il valore di `cCodeInfos` con il valore del parametro `cchName`. Se il valore `cCodeInfos`, diviso per la dimensione di una struttura `COR_PRF_CODE_INFO`, è inferiore a `pcCodeInfos`, allocare un buffer `codeInfos` più grande, aggiornare `cCodeInfos` con la nuova dimensione e chiamare nuovamente `GetCodeInfo2`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetCodeInfo2` con un buffer `codeInfos` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer `codeInfos` sul valore restituito in `pcCodeInfos` moltiplicato per la dimensione di una struttura `COR_PRF_CODE_INFO` e chiamare di nuovo `GetCodeInfo2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetCodeInfo3](icorprofilerinfo4-getcodeinfo3-method.md)
- [Interfaccia ICorProfilerInfo2](icorprofilerinfo2-interface.md)
- [Interfacce di profilatura](profiling-interfaces.md)
- [Profilatura](index.md)
