---
title: Metodo IMethodMalloc::Alloc
ms.date: 03/30/2017
api_name:
- IMethodMalloc.Alloc
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- IMethodMalloc::Alloc
helpviewer_keywords:
- IMethodMalloc::Alloc method [.NET Framework profiling]
- Alloc method, IMethodMalloc interface [.NET Framework profiling]
ms.assetid: 8653bd4c-2290-43d2-a3e1-cbbd50033f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a676989bdc6866f85fabe3e15b1e6b7b8b5a9a9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000714"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="1fff8-102">Metodo IMethodMalloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="1fff8-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="1fff8-103">Tenta di allocare una quantità di memoria specificata per un nuovo corpo di funzione Microsoft intermediate language (MSIL).</span><span class="sxs-lookup"><span data-stu-id="1fff8-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="1fff8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1fff8-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="1fff8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1fff8-105">Parameters</span></span>

`cb`\
<span data-ttu-id="1fff8-106">[in] Il numero di byte da allocare per il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="1fff8-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="1fff8-107">Note</span><span class="sxs-lookup"><span data-stu-id="1fff8-107">Remarks</span></span>

 <span data-ttu-id="1fff8-108">La memoria allocata inizierà con un indirizzo maggiore l'indirizzo di base del modulo che è associato questo allocatore.</span><span class="sxs-lookup"><span data-stu-id="1fff8-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="1fff8-109">In altre parole, ogni allocatore viene creato per un modulo specifico e tenterà di allocare memoria in corrispondenza di un offset positivi dal relativo indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="1fff8-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="1fff8-110">Se `Alloc` non riesce ad allocare il numero richiesto di byte in corrispondenza di un indirizzo maggiore l'indirizzo di base del modulo, viene restituito E_OUTOFMEMORY, indipendentemente dalla quantità effettiva di spazio di memoria disponibile.</span><span class="sxs-lookup"><span data-stu-id="1fff8-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="1fff8-111">Il `Alloc` metodo deve essere usato in combinazione con il [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="1fff8-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="1fff8-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1fff8-112">Requirements</span></span>
 <span data-ttu-id="1fff8-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1fff8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

 <span data-ttu-id="1fff8-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1fff8-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="1fff8-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1fff8-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="1fff8-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fff8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="1fff8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1fff8-117">See also</span></span>

- [<span data-ttu-id="1fff8-118">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="1fff8-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)