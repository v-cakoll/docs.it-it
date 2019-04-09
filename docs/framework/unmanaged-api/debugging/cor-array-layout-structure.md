---
title: Struttura COR_ARRAY_LAYOUT
ms.date: 03/30/2017
api_name:
- COR_ARRAY_LAYOUT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_ARRAY_LAYOUT
helpviewer_keywords:
- COR_DEBUG_IL_TO_NATIVE_MAP structure [.NET Framework debugging]
ms.assetid: aa20ac3d-6f60-4aa2-91c5-f3a86f82eba8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3a5a5bb26912c87cdf37ba0d8f0cee1cf1ffa97
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59142012"
---
# <a name="corarraylayout-structure"></a><span data-ttu-id="f17b9-102">Struttura COR_ARRAY_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="f17b9-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="f17b9-103">Fornisce informazioni sul layout di un oggetto Array in memoria.</span><span class="sxs-lookup"><span data-stu-id="f17b9-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f17b9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f17b9-104">Syntax</span></span>  
  
```  
typedef struct COR_ARRAY_LAYOUT {  
    COR_TYPEID componentID;  
    CorElementType componentType;  
    ULONG32 firstElementOffset;  
    ULONG32 elementSize;  
    ULONG32 countOffset;   
    ULONG32 rankSize;   
    ULONG32 numRanks;   
    ULONG32 rankOffset;   
} COR_ARRAY_LAYOUT;  
```  
  
## <a name="members"></a><span data-ttu-id="f17b9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f17b9-105">Members</span></span>  
  
|<span data-ttu-id="f17b9-106">Member</span><span class="sxs-lookup"><span data-stu-id="f17b9-106">Member</span></span>|<span data-ttu-id="f17b9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f17b9-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="f17b9-108">L'identificatore del tipo di oggetti che contiene la matrice.</span><span class="sxs-lookup"><span data-stu-id="f17b9-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="f17b9-109">Un valore di enumerazione CorElementType che indica se il componente è un riferimento di garbage collection, una classe di valore o una primitiva.</span><span class="sxs-lookup"><span data-stu-id="f17b9-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="f17b9-110">Offset al primo elemento nella matrice.</span><span class="sxs-lookup"><span data-stu-id="f17b9-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="f17b9-111">Le dimensioni di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="f17b9-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="f17b9-112">L'offset per il numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="f17b9-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="f17b9-113">Le dimensioni di rango, in byte.</span><span class="sxs-lookup"><span data-stu-id="f17b9-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="f17b9-114">Il numero di ranghi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="f17b9-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="f17b9-115">L'offset in corrispondenza del quale iniziare la posizione in classifica.</span><span class="sxs-lookup"><span data-stu-id="f17b9-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f17b9-116">Note</span><span class="sxs-lookup"><span data-stu-id="f17b9-116">Remarks</span></span>  
 <span data-ttu-id="f17b9-117">Il `rankSize` campo specifica la dimensione di un ordine di priorità in una matrice multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="f17b9-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="f17b9-118">È preciso per le matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="f17b9-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="f17b9-119">Il valore di `numRanks` è 1 per una matrice unidimensionale e `N` per una matrice multidimensionale di `N` dimensioni.</span><span class="sxs-lookup"><span data-stu-id="f17b9-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f17b9-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f17b9-120">Requirements</span></span>  
 <span data-ttu-id="f17b9-121">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f17b9-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f17b9-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f17b9-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f17b9-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f17b9-123">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f17b9-124">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f17b9-124">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f17b9-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f17b9-125">See also</span></span>

- [<span data-ttu-id="f17b9-126">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f17b9-126">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="f17b9-127">Debug</span><span class="sxs-lookup"><span data-stu-id="f17b9-127">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
