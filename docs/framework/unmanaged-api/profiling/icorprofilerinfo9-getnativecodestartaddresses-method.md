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
# <a name="icorprofilerinfo9getnativecodestartaddresses-method"></a><span data-ttu-id="4baef-102">Metodo ICorProfilerInfo9:: GetNativeCodeStartAddresses</span><span class="sxs-lookup"><span data-stu-id="4baef-102">ICorProfilerInfo9::GetNativeCodeStartAddresses Method</span></span>
  
 <span data-ttu-id="4baef-103">Dato un functionId e rejitId, enumera l'indirizzo iniziale del codice nativo di tutte le versioni compilato JIT del codice attualmente esistente.</span><span class="sxs-lookup"><span data-stu-id="4baef-103">Given a functionId and rejitId, enumerates the native code start address of all jitted versions of this code that currently exist.</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="4baef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4baef-104">Syntax</span></span>  
  
```cpp
HRESULT GetNativeCodeStartAddresses( [in]  FunctionID functionID,
                                     [in]  ReJITID reJitId,
                                     [in]  ULONG32 cCodeStartAddresses,
                                     [out] ULONG32 *pcCodeStartAddresses,
                                     [out] UINT_PTR codeStartAddresses[]);
```  
  
#### <a name="parameters"></a><span data-ttu-id="4baef-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4baef-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4baef-106">in ID della funzione i cui indirizzi di avvio del codice nativo devono essere restituiti.</span><span class="sxs-lookup"><span data-stu-id="4baef-106">[in] The ID of the function whose native code start addresses should be returned.</span></span>  
  
 `reJitId`  
 <span data-ttu-id="4baef-107">[in] Identità della funzione ricompilata in JIT.</span><span class="sxs-lookup"><span data-stu-id="4baef-107">[in] The identity of the JIT-recompiled function.</span></span> 
  
 `cCodeStartAddresses` \
 <span data-ttu-id="4baef-108">[in] Dimensione massima della matrice `codeStartAddresses`.</span><span class="sxs-lookup"><span data-stu-id="4baef-108">[in] The maximum size of the `codeStartAddresses` array.</span></span>

 `pcCodeStartAddresses` \
 <span data-ttu-id="4baef-109">out Numero di indirizzi disponibili.</span><span class="sxs-lookup"><span data-stu-id="4baef-109">[out] The number of available addresses.</span></span>

 `codeStartAddresses` \
 <span data-ttu-id="4baef-110">out Matrice di `UINT_PTR`, ciascuno dei quali è l'indirizzo iniziale per un corpo nativo per la funzione specificata.</span><span class="sxs-lookup"><span data-stu-id="4baef-110">[out] An array of `UINT_PTR`, each one of which is the start address for a native body for the specified function.</span></span> 

## <a name="remarks"></a><span data-ttu-id="4baef-111">Note</span><span class="sxs-lookup"><span data-stu-id="4baef-111">Remarks</span></span>  
 <span data-ttu-id="4baef-112">Quando è abilitata la compilazione a più livelli, una funzione può avere più di un corpo del codice nativo.</span><span class="sxs-lookup"><span data-stu-id="4baef-112">When tiered compilation is enabled, a function may have more than one native code body.</span></span> 

## <a name="requirements"></a><span data-ttu-id="4baef-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4baef-113">Requirements</span></span>  
 <span data-ttu-id="4baef-114">**Piattaforme** Vedere [sistemi operativi supportati da .NET Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="4baef-114">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="4baef-115">**Intestazione:** CorProf. idl, CorProf. h</span><span class="sxs-lookup"><span data-stu-id="4baef-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4baef-116">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4baef-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4baef-117">**Versioni di .NET:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4baef-117">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-22-md.md)]</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4baef-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4baef-118">See also</span></span>
- [<span data-ttu-id="4baef-119">Interfaccia ICorProfilerInfo9</span><span class="sxs-lookup"><span data-stu-id="4baef-119">ICorProfilerInfo9 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo9-interface.md)

