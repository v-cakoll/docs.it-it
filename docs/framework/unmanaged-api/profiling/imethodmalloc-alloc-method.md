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
ms.openlocfilehash: a82a2150f32b1b335da083ca235ed9d2966a0b6e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84494202"
---
# <a name="imethodmallocalloc-method"></a><span data-ttu-id="fbe48-102">Metodo IMethodMalloc::Alloc</span><span class="sxs-lookup"><span data-stu-id="fbe48-102">IMethodMalloc::Alloc Method</span></span>

<span data-ttu-id="fbe48-103">Tenta di allocare una quantità specificata di memoria per un nuovo corpo della funzione MSIL (Microsoft Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="fbe48-103">Attempts to allocate a specified amount of memory for a new Microsoft intermediate language (MSIL) function body.</span></span>

## <a name="syntax"></a><span data-ttu-id="fbe48-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbe48-104">Syntax</span></span>

```cpp
PVOID Alloc (
    [in] ULONG   cb
);
```

## <a name="parameters"></a><span data-ttu-id="fbe48-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="fbe48-105">Parameters</span></span>

`cb`\
<span data-ttu-id="fbe48-106">in Numero di byte da allocare per il corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="fbe48-106">[in] The number of bytes to allocate for the method body.</span></span>

## <a name="remarks"></a><span data-ttu-id="fbe48-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fbe48-107">Remarks</span></span>

 <span data-ttu-id="fbe48-108">La memoria allocata inizierà in corrispondenza di un indirizzo maggiore dell'indirizzo di base del modulo associato a questo allocatore.</span><span class="sxs-lookup"><span data-stu-id="fbe48-108">The allocated memory will begin at an address greater than the base address of the module that is associated with this allocator.</span></span> <span data-ttu-id="fbe48-109">In altre parole, ogni allocatore viene creato per un particolare modulo e tenterà di allocare memoria a un offset positivo dal relativo indirizzo di base.</span><span class="sxs-lookup"><span data-stu-id="fbe48-109">In other words, each allocator is created for a particular module, and will attempt to allocate memory at a positive offset from its base address.</span></span> <span data-ttu-id="fbe48-110">Se `Alloc` non riesce ad allocare il numero richiesto di byte in un indirizzo maggiore dell'indirizzo di base del modulo, restituisce E_OUTOFMEMORY, indipendentemente dalla quantità effettiva di spazio di memoria disponibile.</span><span class="sxs-lookup"><span data-stu-id="fbe48-110">If `Alloc` fails to allocate the requested number of bytes at an address greater than the base address of the module, it returns E_OUTOFMEMORY, regardless of the actual amount of memory space available.</span></span>

 <span data-ttu-id="fbe48-111">Il `Alloc` metodo deve essere usato in combinazione con il metodo [ICorProfilerInfo:: SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) .</span><span class="sxs-lookup"><span data-stu-id="fbe48-111">The `Alloc` method should be used in conjunction with the [ICorProfilerInfo::SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="fbe48-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbe48-112">Requirements</span></span>
 <span data-ttu-id="fbe48-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbe48-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="fbe48-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fbe48-114">**Header:** CorProf.idl, CorProf.h</span></span>

 <span data-ttu-id="fbe48-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbe48-115">**Library:** CorGuids.lib</span></span>

 <span data-ttu-id="fbe48-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbe48-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fbe48-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbe48-117">See also</span></span>

- [<span data-ttu-id="fbe48-118">Interfaccia IMethodMalloc</span><span class="sxs-lookup"><span data-stu-id="fbe48-118">IMethodMalloc Interface</span></span>](imethodmalloc-interface.md)
