---
title: Metodo ICorDebugAssembly3::GetContainerAssembly
ms.date: 03/30/2017
ms.assetid: f5fddeb6-b82e-4ebb-b432-849ce8513c77
ms.openlocfilehash: 969cca6d5613670fc4b26fc973785b4874c3684c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76778063"
---
# <a name="icordebugassembly3getcontainerassembly-method"></a><span data-ttu-id="b9ec0-102">Metodo ICorDebugAssembly3::GetContainerAssembly</span><span class="sxs-lookup"><span data-stu-id="b9ec0-102">ICorDebugAssembly3::GetContainerAssembly Method</span></span>
<span data-ttu-id="b9ec0-103">Restituisce l'assembly del contenitore di questo oggetto `ICorDebugAssembly3`.</span><span class="sxs-lookup"><span data-stu-id="b9ec0-103">Returns the container assembly of this `ICorDebugAssembly3` object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9ec0-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9ec0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetContainerAssembly(  
    ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9ec0-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9ec0-105">Parameters</span></span>  
 `ppAssembly`  
 <span data-ttu-id="b9ec0-106">Puntatore all'indirizzo di un oggetto ICorDebugAssembly che rappresenta l'assembly del contenitore oppure **null** se la chiamata al metodo ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="b9ec0-106">A pointer to the address of an ICorDebugAssembly object that represents the container assembly, or **null** if the method call fails.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9ec0-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="b9ec0-107">Return Value</span></span>  
 <span data-ttu-id="b9ec0-108">`S_OK` se la chiamata al metodo ha esito positivo; in caso contrario, `S_FALSE`e `ppAssembly` sono **null**.</span><span class="sxs-lookup"><span data-stu-id="b9ec0-108">`S_OK` if the method call succeeds; otherwise, `S_FALSE`, and `ppAssembly` is **null**.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9ec0-109">Note</span><span class="sxs-lookup"><span data-stu-id="b9ec0-109">Remarks</span></span>  
 <span data-ttu-id="b9ec0-110">Se l'assembly è stato unito ad altri assembly in un singolo assembly del contenitore, il metodo restituisce l'assembly del contenitore.</span><span class="sxs-lookup"><span data-stu-id="b9ec0-110">If this assembly has been merged with others inside a single container assembly, this method returns the container assembly.</span></span> <span data-ttu-id="b9ec0-111">Per ulteriori informazioni e terminologia, vedere l'argomento [Metodo icordebugprocess6:: EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) .</span><span class="sxs-lookup"><span data-stu-id="b9ec0-111">For more information and terminology, see the [ICorDebugProcess6::EnableVirtualModuleSplitting](icordebugprocess6-enablevirtualmodulesplitting-method.md) topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b9ec0-112">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="b9ec0-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9ec0-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="b9ec0-113">Requirements</span></span>  
 <span data-ttu-id="b9ec0-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9ec0-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9ec0-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9ec0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9ec0-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9ec0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9ec0-117">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9ec0-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9ec0-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b9ec0-118">See also</span></span>

- [<span data-ttu-id="b9ec0-119">Interfaccia ICorDebugAssembly3</span><span class="sxs-lookup"><span data-stu-id="b9ec0-119">ICorDebugAssembly3 Interface</span></span>](icordebugassembly3-interface.md)
- [<span data-ttu-id="b9ec0-120">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="b9ec0-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
