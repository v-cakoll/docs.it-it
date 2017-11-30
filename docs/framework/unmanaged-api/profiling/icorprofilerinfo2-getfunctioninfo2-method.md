---
title: Metodo ICorProfilerInfo2::GetFunctionInfo2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetFunctionInfo2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetFunctionInfo2
helpviewer_keywords:
- GetFunctionInfo2 method [.NET Framework profiling]
- ICorProfilerInfo2::GetFunctionInfo2 method [.NET Framework profiling]
ms.assetid: 0aa60f24-8bbd-4c83-83c5-86ad191b1d82
topic_type: apiref
caps.latest.revision: "18"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b0c288b88c868bc6e324ec57b3956344f03f34e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getfunctioninfo2-method"></a>Metodo ICorProfilerInfo2::GetFunctionInfo2
Ottiene la classe padre, il token di metadati e l'elemento `ClassID` di ciascun argomento di tipo, se presente, di una funzione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFunctionInfo2(  
    [in]  FunctionID funcId,  
    [in]  COR_PRF_FRAME_INFO frameInfo,  
    [out] ClassID *pClassId,  
    [out] ModuleID *pModuleId,  
    [out] mdToken *pToken,  
    [in]  ULONG32 cTypeArgs,  
    [out] ULONG32 *pcTypeArgs,  
    [out] ClassID typeArgs[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `funcId`  
 [in] ID della funzione per cui ottenere la classe padre e altre informazioni.  
  
 `frameInfo`  
 [in] Valore `COR_PRF_FRAME_INFO` che punta alle informazioni su uno stack frame.  
  
 `pClassId`  
 [out] Puntatore alla classe padre della funzione.  
  
 `pModuleId`  
 [out] Puntatore al modulo in cui è definita la classe padre della funzione.  
  
 `pToken`  
 [out] Puntatore al token di metadati per la funzione.  
  
 `cTypeArgs`  
 [in] Dimensione della matrice `typeArgs`.  
  
 `pcTypeArgs`  
 [out] Puntatore al numero complessivo di valori `ClassID`.  
  
 `typeArgs`  
 [out] Matrice di valori `ClassID`, ognuno dei quali è l'ID di un argomento di tipo della funzione. Dopo il completamento del metodo, `typeArgs` conterrà tutti i valori `ClassID` o alcuni di essi.  
  
## <a name="remarks"></a>Note  
 Il codice del profiler può chiamare [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) per ottenere un [metadati](../../../../docs/framework/unmanaged-api/metadata/index.md) interfaccia per un determinato modulo. Il token di metadati restituito nella posizione a cui fa riferimento `pToken` può quindi essere usato per accedere ai metadati per la funzione.  
  
 L'ID classe e gli argomenti di tipo restituiti tramite i parametri `pClassId` e `typeArgs` dipendono dal valore passato nel parametro `frameInfo`, come illustrato nella tabella seguente.  
  
|Valore del parametro `frameInfo`|Risultato|  
|----------------------------------------|------------|  
|Valore `COR_PRF_FRAME_INFO` ottenuto da un callback di `FunctionEnter2`|L'elemento `ClassID`, restituito nella posizione a cui fa riferimento `pClassId`, e tutti gli argomenti di tipo, restituiti nella matrice `typeArgs`, saranno determinati in modo esatto.|  
|Valore `COR_PRF_FRAME_INFO` ottenuto da un'origine diversa da un callback di `FunctionEnter2`|Non è possibile determinare in modo esatto l'elemento `ClassID` e gli argomenti di tipo. Ciò significa che `ClassID` potrebbe essere null e che alcuni argomenti di tipo potrebbero venire restituiti come <xref:System.Object>.|  
|Zero|Non è possibile determinare in modo esatto l'elemento `ClassID` e gli argomenti di tipo. Ciò significa che `ClassID` potrebbe essere null e che alcuni argomenti di tipo potrebbero venire restituiti come <xref:System.Object>.|  
  
 Dopo il completamento del metodo `GetFunctionInfo2`, è necessario verificare che il buffer `typeArgs` sia abbastanza grande per contenere tutti i valori `ClassID`. A tale scopo, confrontare il valore a cui punta `pcTypeArgs` con il valore del parametro `cTypeArgs`. Se `pcTypeArgs` punta a un valore maggiore di `cTypeArgs` diviso per la dimensione di un valore `ClassID`, allocare un buffer `pcTypeArgs` più grande, aggiornare `cTypeArgs` con la nuova dimensione e chiamare nuovamente `GetFunctionInfo2`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetFunctionInfo2` con un buffer `pcTypeArgs` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito in `pcTypeArgs` diviso per la dimensione di un valore `ClassID` e chiamare di nuovo `GetFunctionInfo2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids.lib  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [Interfaccia ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
