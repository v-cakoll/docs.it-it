---
title: Struttura COR_PRF_FUNCTION_ARGUMENT_INFO
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_FUNCTION_ARGUMENT_INFO
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords: COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e26377fe3c5cfbae68f90087e3fb624ae4db0dc8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="corprffunctionargumentinfo-structure"></a><span data-ttu-id="49f91-102">Struttura COR_PRF_FUNCTION_ARGUMENT_INFO</span><span class="sxs-lookup"><span data-stu-id="49f91-102">COR_PRF_FUNCTION_ARGUMENT_INFO Structure</span></span>
<span data-ttu-id="49f91-103">Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.</span><span class="sxs-lookup"><span data-stu-id="49f91-103">Represents a function's arguments, in left-to-right order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49f91-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="49f91-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a><span data-ttu-id="49f91-105">Membri</span><span class="sxs-lookup"><span data-stu-id="49f91-105">Members</span></span>  
  
|<span data-ttu-id="49f91-106">Membro</span><span class="sxs-lookup"><span data-stu-id="49f91-106">Member</span></span>|<span data-ttu-id="49f91-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="49f91-107">Description</span></span>|  
|------------|-----------------|  
|`numRanges`|<span data-ttu-id="49f91-108">Il numero di blocchi di argomenti.</span><span class="sxs-lookup"><span data-stu-id="49f91-108">The number of blocks of arguments.</span></span> <span data-ttu-id="49f91-109">Questo valore è il numero di [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) strutture nel `ranges` matrice.</span><span class="sxs-lookup"><span data-stu-id="49f91-109">That is, this value is the number of [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structures in the `ranges` array.</span></span>|  
|`totalArgumentSize`|<span data-ttu-id="49f91-110">Le dimensioni totali di tutti gli argomenti.</span><span class="sxs-lookup"><span data-stu-id="49f91-110">The total size of all arguments.</span></span> <span data-ttu-id="49f91-111">In altre parole, questo valore è la somma delle lunghezze degli argomenti.</span><span class="sxs-lookup"><span data-stu-id="49f91-111">In other words, this value is the sum of the argument lengths.</span></span>|  
|`ranges`|<span data-ttu-id="49f91-112">Matrice di `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuno dei quali rappresenta un blocco di argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="49f91-112">An array of `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which represents one block of function arguments.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="49f91-113">Note</span><span class="sxs-lookup"><span data-stu-id="49f91-113">Remarks</span></span>  
 <span data-ttu-id="49f91-114">Una funzione può avere un numero di argomenti.</span><span class="sxs-lookup"><span data-stu-id="49f91-114">A function may have many arguments.</span></span> <span data-ttu-id="49f91-115">Gli argomenti potrebbero non essere archiviati in modo contiguo nella memoria.</span><span class="sxs-lookup"><span data-stu-id="49f91-115">Those arguments might not be stored contiguously in memory.</span></span> <span data-ttu-id="49f91-116">Potrebbe essere un blocco di tre argomenti in un'unica posizione, un blocco di due argomenti in un'altra posizione e un blocco finale di un argomento in una posizione diversa.</span><span class="sxs-lookup"><span data-stu-id="49f91-116">You might have a block of three arguments in one place, a block of two arguments in another place, and a final block of one argument in a different place.</span></span> <span data-ttu-id="49f91-117">Questi argomenti sono tutti della stessa funzione; sono archiviati solo in posizioni diverse.</span><span class="sxs-lookup"><span data-stu-id="49f91-117">These arguments are all for the same function; they're just stored in different places.</span></span>  
  
 <span data-ttu-id="49f91-118">Il `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura rappresenta tutti gli argomenti di una singola funzione.</span><span class="sxs-lookup"><span data-stu-id="49f91-118">The `COR_PRF_FUNCTION_ARGUMENT_INFO` structure represents all the arguments of a single function.</span></span> <span data-ttu-id="49f91-119">Usa una matrice per fare riferimento a tutti i blocchi di argomenti della funzione.</span><span class="sxs-lookup"><span data-stu-id="49f91-119">It uses an array to reference all the blocks of function arguments.</span></span> <span data-ttu-id="49f91-120">In tal caso, per una singola funzione, è una singola `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura, a cui fa riferimento a più `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuno dei quali punta a uno o più argomenti di funzione.</span><span class="sxs-lookup"><span data-stu-id="49f91-120">So, for a single function, you have a single `COR_PRF_FUNCTION_ARGUMENT_INFO` structure, which references multiple `COR_PRF_FUNCTION_ARGUMENT_RANGE` structures, each of which points to one or more function arguments.</span></span>  
  
 <span data-ttu-id="49f91-121">Gli argomenti che vengono archiviati nei registri vengono passati in memoria per compilare le strutture.</span><span class="sxs-lookup"><span data-stu-id="49f91-121">Arguments that are stored in registers are spilled into memory to build the structures.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49f91-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="49f91-122">Requirements</span></span>  
 <span data-ttu-id="49f91-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="49f91-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49f91-124">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="49f91-124">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="49f91-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49f91-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49f91-126">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49f91-126">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="49f91-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="49f91-127">See Also</span></span>  
 [<span data-ttu-id="49f91-128">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="49f91-128">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
