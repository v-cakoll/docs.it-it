---
title: Metodo ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080956"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a><span data-ttu-id="bb61d-102">Metodo ICorDebugAssembly3::EnumerateContainedAssemblies</span><span class="sxs-lookup"><span data-stu-id="bb61d-102">ICorDebugAssembly3::EnumerateContainedAssemblies Method</span></span>
<span data-ttu-id="bb61d-103">Ottiene un enumeratore per gli assembly contenuti in questo assembly.</span><span class="sxs-lookup"><span data-stu-id="bb61d-103">Gets an enumerator for the assemblies contained in this assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb61d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bb61d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb61d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bb61d-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="bb61d-106">[out] Un puntatore all'indirizzo di un oggetto di interfaccia ICorDebugAssemblyEnum che corrisponde all'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="bb61d-106">[out] A pointer to the address of an ICorDebugAssemblyEnum interface object that is the enumerator.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bb61d-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bb61d-107">Return Value</span></span>  
 `S_OK` <span data-ttu-id="bb61d-108">Se l'oggetto `ICorDebugAssembly3` oggetto è un contenitore; in caso contrario, `S_FALSE`, e l'enumerazione è vuota.</span><span class="sxs-lookup"><span data-stu-id="bb61d-108">if this `ICorDebugAssembly3` object is a container; otherwise, `S_FALSE`, and the enumeration is empty.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb61d-109">Note</span><span class="sxs-lookup"><span data-stu-id="bb61d-109">Remarks</span></span>  
 <span data-ttu-id="bb61d-110">I simboli sono necessari per enumerare gli assembly contenuti.</span><span class="sxs-lookup"><span data-stu-id="bb61d-110">Symbols are needed to enumerate the contained assemblies.</span></span> <span data-ttu-id="bb61d-111">Se non ce ne sono, il metodo restituisce `S_FALSE` e non viene fornito alcun enumeratore valido.</span><span class="sxs-lookup"><span data-stu-id="bb61d-111">If they aren't present, the method returns `S_FALSE`, and no valid enumerator is provided.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bb61d-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="bb61d-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb61d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bb61d-113">Requirements</span></span>  
 <span data-ttu-id="bb61d-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb61d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb61d-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb61d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb61d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb61d-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bb61d-117">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bb61d-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bb61d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bb61d-118">See also</span></span>

- [<span data-ttu-id="bb61d-119">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="bb61d-119">ICorDebugAssembly3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [<span data-ttu-id="bb61d-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="bb61d-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
