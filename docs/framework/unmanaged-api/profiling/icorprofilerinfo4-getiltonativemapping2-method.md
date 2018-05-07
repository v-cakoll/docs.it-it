---
title: Metodo ICorProfilerInfo4::GetILToNativeMapping2
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetILToNativeMapping2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2
helpviewer_keywords:
- ICorProfilerInfo4::GetILToNativeMapping2 method [.NET Framework profiling]
- GetILToNativeMapping2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 756c1c25-08a7-4060-9798-dbeaa2f3bee5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fba81500749a16a59405edaaa2ee1d12d86229f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo4getiltonativemapping2-method"></a>Metodo ICorProfilerInfo4::GetILToNativeMapping2
Ottiene una mappa dagli offset MSIL (Microsoft Intermediate Language) agli offset nativi per il codice contenuto nella versione ricompilata in JIT della funzione specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetILToNativeMapping(  
    [in] FunctionID functionId,  
    [in] ReJITID reJitId,  
    [in] ULONG32 cMap,  
    [out] ULONG32 *pcMap,  
    [out, size_is(cMap), length_is(*pcMap)]  
        COR_DEBUG_IL_TO_NATIVE_MAP map[]);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] ID della funzione che contiene il codice.  
  
 `pReJitId`  
 [in] Identità della funzione ricompilata in JIT. L'identità deve essere uguale a zero in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
 `cMap`  
 [in] Dimensione massima della matrice `map`.  
  
 `pcMap`  
 [out] Numero totale di strutture COR_DEBUG_IL_TO_NATIVE_MAP disponibili.  
  
 `map`  
 [out] Matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`, ognuna delle quali specifica gli offset. Dopo il completamento del metodo `GetILToNativeMapping2`, `map` conterrà alcune o tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`.  
  
## <a name="remarks"></a>Note  
 `GetILToNativeMapping2` è simile per la [ICorProfilerInfo:: GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md) metodo, ad eccezione del fatto che consentirà al profiler di specificare l'ID della funzione ricompilata in futuro rilascia.  
  
> [!NOTE]
>  Il [icorprofilerfunctioncontrol:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctioncontrol-setilinstrumentedcodemap-method.md) metodo non è implementato nel [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], pertanto le funzioni che sono stati ricompilata in JIT non possono avere un mapping per IL codice nativo che differisce dall'originariamente funzione compilata. Di conseguenza, `GetILToNativeMapping2` non può essere chiamato con un ID ricompilato in JIT diverso da zero in [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)].  
  
 Il metodo `GetILToNativeMapping2` restituisce una matrice di strutture `COR_DEBUG_IL_TO_NATIVE_MAP`. Per indicare che determinati intervalli di istruzioni native corrispondono ad aree speciali del codice, ad esempio, il prologo, una voce nella matrice può avere il `ilOffset` campo impostato su un valore di [CorDebugIlToNativeMappingTypes](../../../../docs/framework/unmanaged-api/debugging/cordebugiltonativemappingtypes-enumeration.md) enumerazione.  
  
 Dopo il completamento del metodo `GetILToNativeMapping2`, è necessario verificare che il buffer `map` sia abbastanza grande per contenere tutte le strutture `COR_DEBUG_IL_TO_NATIVE_MAP`. A tale scopo, confrontare il valore di `cMap` con il valore del parametro `pcMap`. Se il valore `pcMap`, moltiplicato per la dimensione di una struttura `COR_DEBUG_IL_TO_NATIVE_MAP`, è superiore a `cMap`, allocare un buffer `map` più grande, aggiornare `cMap` con la nuova dimensione e chiamare nuovamente `GetILToNativeMapping2`.  
  
 In alternativa, è possibile chiamare innanzitutto `GetILToNativeMapping2` con un buffer `map` di lunghezza zero per ottenere le dimensioni del buffer corrette. È quindi possibile impostare le dimensioni del buffer sul valore restituito nel parametro `pcMap` e chiamare nuovamente `GetILToNativeMapping2`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetILToNativeMapping](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)  
 [Interfaccia ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)  
 [Interfacce di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilatura](../../../../docs/framework/unmanaged-api/profiling/index.md)
