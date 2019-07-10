---
title: Metodo ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05c4e2a5c16f11f80cc8356a65b746eab81a3899
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67744405"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="be72a-102">Metodo ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="be72a-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="be72a-103">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="be72a-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be72a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="be72a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be72a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="be72a-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="be72a-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugAssemblyEnum che corrisponde all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="be72a-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="be72a-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="be72a-107">Return Value</span></span>  
 <span data-ttu-id="be72a-108">`S_OK` se questo oggetto `ICorDebugAssembly3` è un contenitore, altrimenti `S_FALSE` e l'enumerazione è vuota.</span><span class="sxs-lookup"><span data-stu-id="be72a-108">`S_OK` if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="be72a-109">Note</span><span class="sxs-lookup"><span data-stu-id="be72a-109">Remarks</span></span>  
 <span data-ttu-id="be72a-110">I simboli sono necessari per enumerare gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="be72a-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="be72a-111">Se non ce ne sono, il metodo restituisce `S_FALSE` e non viene fornito alcun enumeratore valido.</span><span class="sxs-lookup"><span data-stu-id="be72a-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="be72a-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="be72a-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be72a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="be72a-113">Requirements</span></span>  
 <span data-ttu-id="be72a-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="be72a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be72a-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="be72a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="be72a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="be72a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="be72a-117">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be72a-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be72a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="be72a-118">See also</span></span>

- [<span data-ttu-id="be72a-119">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="be72a-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="be72a-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="be72a-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
