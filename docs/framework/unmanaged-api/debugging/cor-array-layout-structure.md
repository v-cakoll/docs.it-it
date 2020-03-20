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
ms.openlocfilehash: ca2d00611a7530dfb0d1c2a27123947bdf69820d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179344"
---
# <a name="cor_array_layout-structure"></a><span data-ttu-id="bbabe-102">Struttura COR_ARRAY_LAYOUT</span><span class="sxs-lookup"><span data-stu-id="bbabe-102">COR_ARRAY_LAYOUT Structure</span></span>
<span data-ttu-id="bbabe-103">Fornisce informazioni sul layout di un oggetto Array in memoria.</span><span class="sxs-lookup"><span data-stu-id="bbabe-103">Provides information about the layout of an array object in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbabe-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bbabe-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="bbabe-105">Members</span><span class="sxs-lookup"><span data-stu-id="bbabe-105">Members</span></span>  
  
|<span data-ttu-id="bbabe-106">Membro</span><span class="sxs-lookup"><span data-stu-id="bbabe-106">Member</span></span>|<span data-ttu-id="bbabe-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbabe-107">Description</span></span>|  
|------------|-----------------|  
|`componentID`|<span data-ttu-id="bbabe-108">Identificatore del tipo di oggetti contenuti nella matrice.</span><span class="sxs-lookup"><span data-stu-id="bbabe-108">The identifier of the type of objects that the array contains.</span></span>|  
|`componentType`|<span data-ttu-id="bbabe-109">Valore di enumerazione CorElementType che indica se il componente è un riferimento di Garbage Collection, una classe di valori o una primitiva.</span><span class="sxs-lookup"><span data-stu-id="bbabe-109">A CorElementType enumeration value that indicates whether the component is a garbage collection reference, a value class, or a primitive.</span></span>|  
|`firstElementOffset`|<span data-ttu-id="bbabe-110">Offset al primo elemento della matrice.</span><span class="sxs-lookup"><span data-stu-id="bbabe-110">The offset to the first element in the array.</span></span>|  
|`elementSize`|<span data-ttu-id="bbabe-111">Dimensione di ogni elemento.</span><span class="sxs-lookup"><span data-stu-id="bbabe-111">The size of each element.</span></span>|  
|`countOffset`|<span data-ttu-id="bbabe-112">Offset del numero di elementi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="bbabe-112">The offset to the number of elements in the array.</span></span>|  
|`rankSize`|<span data-ttu-id="bbabe-113">Dimensione del rango, in byte.</span><span class="sxs-lookup"><span data-stu-id="bbabe-113">The size of the rank, in bytes.</span></span>|  
|`numRanks`|<span data-ttu-id="bbabe-114">Numero di ranghi nella matrice.</span><span class="sxs-lookup"><span data-stu-id="bbabe-114">The number of ranks in the array.</span></span>|  
|`rankOffset`|<span data-ttu-id="bbabe-115">Offset in corrispondenza del quale iniziano i ranghi.</span><span class="sxs-lookup"><span data-stu-id="bbabe-115">The offset at which the ranks start.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbabe-116">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="bbabe-116">Remarks</span></span>  
 <span data-ttu-id="bbabe-117">Il `rankSize` campo specifica la dimensione di una classificazione in una matrice multidimensionale.</span><span class="sxs-lookup"><span data-stu-id="bbabe-117">The `rankSize` field specifies the size of a rank in a multi-dimensional array.</span></span> <span data-ttu-id="bbabe-118">È preciso anche per le matrici unidimensionali.</span><span class="sxs-lookup"><span data-stu-id="bbabe-118">It is accurate for single-dimensional arrays as well.</span></span>  
  
 <span data-ttu-id="bbabe-119">Il valore `numRanks` di è 1 per `N` una matrice unidimensionale e per una matrice multidimensionale di `N` dimensioni.</span><span class="sxs-lookup"><span data-stu-id="bbabe-119">The value of `numRanks` is 1 for a single-dimensional array and `N` for a multi-dimensional array of `N` dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbabe-120">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bbabe-120">Requirements</span></span>  
 <span data-ttu-id="bbabe-121">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbabe-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbabe-122">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bbabe-122">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bbabe-123">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbabe-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbabe-124">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbabe-124">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbabe-125">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bbabe-125">See also</span></span>

- [<span data-ttu-id="bbabe-126">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="bbabe-126">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="bbabe-127">Debug</span><span class="sxs-lookup"><span data-stu-id="bbabe-127">Debugging</span></span>](index.md)
