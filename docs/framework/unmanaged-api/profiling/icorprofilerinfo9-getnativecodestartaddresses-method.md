---
title: ICorProfilerInfo9::GetNativeCodeStartAddresses
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo9.GetNativeCodeStartAddresses
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: f5c7f11a322e4cf3ed38608e0f380dd632bc8fb6
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2019
ms.locfileid: "68973811"
---
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a>Metodo ICorProfilerInfo9:: GetNativeCodeStartAddresses
  
 Dato un functionId e rejitId, enumera l'indirizzo iniziale del codice nativo di tutte le versioni compilato JIT del codice attualmente esistente.   
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 in ID della funzione i cui indirizzi di avvio del codice nativo devono essere restituiti.  
  
 `reJitId`  
 [in] Identità della funzione ricompilata in JIT. 
  
 `cCodeStartAddresses` \
 [in] Dimensione massima della matrice `codeStartAddresses`.

 `pcCodeStartAddresses` \
 out Numero di indirizzi disponibili.

 `codeStartAddresses` \
 out Matrice di `UINT_PTR`, ciascuno dei quali è l'indirizzo iniziale per un corpo nativo per la funzione specificata. 

## <a name="remarks"></a>Note  
 Quando è abilitata la compilazione a più livelli, una funzione può avere più di un corpo del codice nativo. 

## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).  
  
 **Intestazione:** CorProf. idl, CorProf. h  
  
 **Libreria** CorGuids.lib  
  
 **Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)] 
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICorProfilerInfo9](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

