---
title: Interfaccia IMethodMalloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc
helpviewer_keywords:
- IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8c8ab5dc-557c-473a-82f2-6e403eca7dac
topic_type:
- apiref
ms.openlocfilehash: e9cbf4551c2f8b183e9e6c37a74b13aff3a19ec1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860969"
---
# <a name="imethodmalloc-interface"></a><span data-ttu-id="f8a40-102">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="f8a40-102">IMethodMalloc Interface</span></span>
<span data-ttu-id="f8a40-103">Fornisce un metodo per allocare memoria per un nuovo corpo della funzione MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="f8a40-103">Provides a method to allocate memory for a new Microsoft intermediate language (MSIL) function body.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f8a40-104">L'interfaccia `IMethodMalloc` è un semplice allocatore di memoria.</span><span class="sxs-lookup"><span data-stu-id="f8a40-104">The `IMethodMalloc` interface is a simple memory allocator.</span></span> <span data-ttu-id="f8a40-105">Consente di allocare memoria, ma non di liberarla.</span><span class="sxs-lookup"><span data-stu-id="f8a40-105">It allows you to allocate memory, but not to free it.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f8a40-106">Metodi</span><span class="sxs-lookup"><span data-stu-id="f8a40-106">Methods</span></span>  
  
|<span data-ttu-id="f8a40-107">Metodo</span><span class="sxs-lookup"><span data-stu-id="f8a40-107">Method</span></span>|<span data-ttu-id="f8a40-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f8a40-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f8a40-109">Metodo Alloc</span><span class="sxs-lookup"><span data-stu-id="f8a40-109">Alloc Method</span></span>](imethodmalloc-alloc-method.md)|<span data-ttu-id="f8a40-110">Tenta di allocare una quantità specificata di memoria per un nuovo corpo della funzione MSIL.</span><span class="sxs-lookup"><span data-stu-id="f8a40-110">Attempts to allocate a specified amount of memory for a new MSIL function body.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f8a40-111">Note</span><span class="sxs-lookup"><span data-stu-id="f8a40-111">Remarks</span></span>  
 <span data-ttu-id="f8a40-112">Ogni allocatore è specifico del modulo e garantisce che il corpo della funzione si trovi in corrispondenza di un offset positivo rispetto alla base del modulo.</span><span class="sxs-lookup"><span data-stu-id="f8a40-112">Each allocator is module-specific and ensures that the function body will be at a positive offset from the base of the module.</span></span> <span data-ttu-id="f8a40-113">La memoria al di sopra della base di un modulo può essere preziosa, quindi l'allocatore deve essere usato per allocare memoria solo per il corpo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="f8a40-113">Memory above the base of a module can be precious, so the allocator should be used to allocate memory only for a function body.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8a40-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f8a40-114">Requirements</span></span>  
 <span data-ttu-id="f8a40-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8a40-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8a40-116">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f8a40-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f8a40-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f8a40-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f8a40-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8a40-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8a40-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8a40-119">See also</span></span>

- [<span data-ttu-id="f8a40-120">Interfacce di profilatura</span><span class="sxs-lookup"><span data-stu-id="f8a40-120">Profiling Interfaces</span></span>](profiling-interfaces.md)
