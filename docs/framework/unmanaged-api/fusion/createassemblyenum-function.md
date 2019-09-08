---
title: Funzione CreateAssemblyEnum
ms.date: 03/30/2017
api_name:
- CreateAssemblyEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyEnum
helpviewer_keywords:
- CreateAssemblyEnum function [.NET Framework fusion]
ms.assetid: 3506df38-6cea-42f6-946e-4287863bcfb3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1db72c44b53b5abff9aee35094abc1e0e577fad4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70795381"
---
# <a name="createassemblyenum-function"></a><span data-ttu-id="99da3-102">Funzione CreateAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="99da3-102">CreateAssemblyEnum Function</span></span>
<span data-ttu-id="99da3-103">Ottiene un puntatore a un'istanza di [IAssemblyEnum](iassemblyenum-interface.md) in grado di enumerare gli oggetti nell'assembly con il [IAssemblyName](iassemblyname-interface.md)specificato.</span><span class="sxs-lookup"><span data-stu-id="99da3-103">Gets a pointer to an [IAssemblyEnum](iassemblyenum-interface.md) instance that can enumerate the objects in the assembly with the specified [IAssemblyName](iassemblyname-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99da3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99da3-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyEnum (  
    [out] IAssemblyEnum  **pEnum,  
    [in]  IUnknown       *pUnkReserved,  
    [in]  IAssemblyName  *pName,  
    [in]  DWORD          dwFlags,  
    [in]  LPVOID         pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="99da3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="99da3-105">Parameters</span></span>  
 `pEnum`  
 <span data-ttu-id="99da3-106">out Puntatore a una posizione di memoria che contiene il `IAssemblyEnum` puntatore richiesto.</span><span class="sxs-lookup"><span data-stu-id="99da3-106">[out] Pointer to a memory location that contains the requested `IAssemblyEnum` pointer.</span></span>  
  
 `pUnkReserved`  
 <span data-ttu-id="99da3-107">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="99da3-107">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="99da3-108">`pUnkReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="99da3-108">`pUnkReserved` must be a null reference.</span></span>  
  
 `pName`  
 <span data-ttu-id="99da3-109">in Oggetto `IAssemblyName` dell'assembly richiesto.</span><span class="sxs-lookup"><span data-stu-id="99da3-109">[in] The `IAssemblyName` of the requested assembly.</span></span> <span data-ttu-id="99da3-110">Questo nome viene usato per filtrare l'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="99da3-110">This name is used to filter the enumeration.</span></span> <span data-ttu-id="99da3-111">Può essere null per enumerare tutti gli assembly nella Global Assembly Cache.</span><span class="sxs-lookup"><span data-stu-id="99da3-111">It can be null to enumerate all assemblies in the global assembly cache.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="99da3-112">in Flag per la modifica del comportamento dell'enumeratore.</span><span class="sxs-lookup"><span data-stu-id="99da3-112">[in] Flags for modifying the enumerator's behavior.</span></span> <span data-ttu-id="99da3-113">Questo parametro contiene esattamente un bit dell'enumerazione [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="99da3-113">This parameter contains exactly one bit from the [ASM_CACHE_FLAGS](asm-cache-flags-enumeration.md) enumeration.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="99da3-114">in Riservato per l'estendibilità futura.</span><span class="sxs-lookup"><span data-stu-id="99da3-114">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="99da3-115">`pvReserved`deve essere un riferimento null.</span><span class="sxs-lookup"><span data-stu-id="99da3-115">`pvReserved` must be a null reference.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99da3-116">Note</span><span class="sxs-lookup"><span data-stu-id="99da3-116">Remarks</span></span>  
 <span data-ttu-id="99da3-117">Il `dwFlags` parametro contiene esattamente un bit `ASM_CACHE_FLAGS` dall'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="99da3-117">The `dwFlags` parameter contains exactly one bit from the `ASM_CACHE_FLAGS` enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="99da3-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="99da3-118">Requirements</span></span>  
 <span data-ttu-id="99da3-119">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="99da3-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="99da3-120">**Intestazione:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="99da3-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="99da3-121">**Libreria** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="99da3-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="99da3-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="99da3-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99da3-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99da3-123">See also</span></span>

- [<span data-ttu-id="99da3-124">Interfaccia IAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="99da3-124">IAssemblyEnum Interface</span></span>](iassemblyenum-interface.md)
- [<span data-ttu-id="99da3-125">Interfaccia IAssemblyName</span><span class="sxs-lookup"><span data-stu-id="99da3-125">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="99da3-126">Funzioni statiche globali Fusion</span><span class="sxs-lookup"><span data-stu-id="99da3-126">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
