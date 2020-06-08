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
ms.openlocfilehash: 9fca75ae59b95a226b51768b3e1bfb220d9926f1
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500962"
---
# <a name="cor_prf_function_argument_info-structure"></a><span data-ttu-id="5e0db-102">Struttura COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="5e0db-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="5e0db-103">Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="5e0db-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e0db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e0db-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="5e0db-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5e0db-105">Members</span></span>  
  
|<span data-ttu-id="5e0db-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5e0db-106">Member</span></span>|<span data-ttu-id="5e0db-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e0db-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="5e0db-108">Numero di blocchi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="5e0db-108">The number of blocks of arguments.</span></span> <span data-ttu-id="5e0db-109">Questo valore corrisponde al numero di strutture [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) nella `ranges` matrice.</span><span class="sxs-lookup"><span data-stu-id="5e0db-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="5e0db-110">Dimensione totale di tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5e0db-110">The total size of all arguments.</span></span> <span data-ttu-id="5e0db-111">In altre parole, questo valore è la somma delle lunghezze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="5e0db-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="5e0db-112">Matrice di `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuna delle quali rappresenta un blocco di argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="5e0db-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e0db-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5e0db-113">Remarks</span></span>  
 <span data-ttu-id="5e0db-114">Una funzione può avere molti argomenti.</span><span class="sxs-lookup"><span data-stu-id="5e0db-114">A function may have many arguments.</span></span> <span data-ttu-id="5e0db-115">Tali argomenti potrebbero non essere archiviati in modo contiguo nella memoria.</span><span class="sxs-lookup"><span data-stu-id="5e0db-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="5e0db-116">Si potrebbe avere un blocco di tre argomenti in un'unica posizione, un blocco di due argomenti in un'altra posizione e un blocco finale di un argomento in una posizione diversa.</span><span class="sxs-lookup"><span data-stu-id="5e0db-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="5e0db-117">Questi argomenti sono tutti per la stessa funzione. sono archiviati solo in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="5e0db-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="5e0db-118">La `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura rappresenta tutti gli argomenti di una singola funzione.</span><span class="sxs-lookup"><span data-stu-id="5e0db-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="5e0db-119">Usa una matrice per fare riferimento a tutti i blocchi degli argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="5e0db-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="5e0db-120">Per una singola funzione, quindi, è presente una singola `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura, che fa riferimento `COR_PRF_FUNCTION_ARGUMENT_RANGE` a più strutture, ognuna delle quali punta a uno o più argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="5e0db-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="5e0db-121">Gli argomenti archiviati nei registri vengono distribuiti in memoria per compilare le strutture.</span><span class="sxs-lookup"><span data-stu-id="5e0db-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e0db-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e0db-122">Requirements</span></span>  
 <span data-ttu-id="5e0db-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e0db-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e0db-124">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="5e0db-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5e0db-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e0db-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e0db-126">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e0db-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e0db-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e0db-127">See also</span></span>

- [<span data-ttu-id="5e0db-128">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="5e0db-128">Profiling Structures</span></span>](profiling-structures.md)
