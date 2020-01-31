---
title: Struttura COR_PRF_FUNCTION_ARGUMENT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
ms.openlocfilehash: c92ee580caed9f1fb87a31b676747769ad31a0e2
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867252"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="edea7-102">Struttura COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="edea7-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="edea7-103">Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="edea7-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="edea7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="edea7-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="edea7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="edea7-105">Members</span></span>  
  
|<span data-ttu-id="edea7-106">Member</span><span class="sxs-lookup"><span data-stu-id="edea7-106">Member</span></span>|<span data-ttu-id="edea7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="edea7-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="edea7-108">Numero di blocchi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="edea7-108">The number of blocks of arguments.</span></span> <span data-ttu-id="edea7-109">Questo valore corrisponde al numero di strutture [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) nella matrice di `ranges`.</span><span class="sxs-lookup"><span data-stu-id="edea7-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="edea7-110">Dimensione totale di tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="edea7-110">The total size of all arguments.</span></span> <span data-ttu-id="edea7-111">In altre parole, questo valore è la somma delle lunghezze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="edea7-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="edea7-112">Matrice di strutture di `COR_PRF_FUNCTION_ARGUMENT_RANGE`, ciascuna delle quali rappresenta un blocco di argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="edea7-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="edea7-113">Note</span><span class="sxs-lookup"><span data-stu-id="edea7-113">Remarks</span></span>  
 <span data-ttu-id="edea7-114">Una funzione può avere molti argomenti.</span><span class="sxs-lookup"><span data-stu-id="edea7-114">A function may have many arguments.</span></span> <span data-ttu-id="edea7-115">Tali argomenti potrebbero non essere archiviati in modo contiguo nella memoria.</span><span class="sxs-lookup"><span data-stu-id="edea7-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="edea7-116">Si potrebbe avere un blocco di tre argomenti in un'unica posizione, un blocco di due argomenti in un'altra posizione e un blocco finale di un argomento in una posizione diversa.</span><span class="sxs-lookup"><span data-stu-id="edea7-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="edea7-117">Questi argomenti sono tutti per la stessa funzione. sono archiviati solo in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="edea7-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="edea7-118">La struttura `COR_PRF_FUNCTION_ARGUMENT_INFO` rappresenta tutti gli argomenti di una singola funzione.</span><span class="sxs-lookup"><span data-stu-id="edea7-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="edea7-119">Usa una matrice per fare riferimento a tutti i blocchi degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="edea7-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="edea7-120">Per una singola funzione, quindi, è disponibile un'unica struttura di `COR_PRF_FUNCTION_ARGUMENT_INFO`, che fa riferimento a più strutture `COR_PRF_FUNCTION_ARGUMENT_RANGE`, ognuna delle quali punta a uno o più argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="edea7-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="edea7-121">Gli argomenti archiviati nei registri vengono distribuiti in memoria per compilare le strutture.</span><span class="sxs-lookup"><span data-stu-id="edea7-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="edea7-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="edea7-122">Requirements</span></span>  
 <span data-ttu-id="edea7-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="edea7-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="edea7-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="edea7-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="edea7-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="edea7-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="edea7-126">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="edea7-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edea7-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="edea7-127">See also</span></span>

- [<span data-ttu-id="edea7-128">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="edea7-128">Profiling Structures</span></span>](profiling-structures.md)
