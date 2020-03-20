---
title: Struttura COR_IL_MAP
ms.date: 03/30/2017
api_name:
- COR_IL_MAP
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_IL_MAP
helpviewer_keywords:
- COR_IL_MAP structure [.NET Framework debugging]
ms.assetid: 534ebc17-963d-4b26-8375-8cd940281db3
topic_type:
- apiref
ms.openlocfilehash: 4c79d0e4e37f3f884651e49c8fff6db72fac4f50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179297"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="fbf3c-102">Struttura COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="fbf3c-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="fbf3c-103">Specifica le modifiche nell'offset relativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf3c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fbf3c-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;
    ULONG32 newOffset;
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="fbf3c-105">Members</span><span class="sxs-lookup"><span data-stu-id="fbf3c-105">Members</span></span>  
  
|<span data-ttu-id="fbf3c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="fbf3c-106">Member</span></span>|<span data-ttu-id="fbf3c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fbf3c-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="fbf3c-108">L'offset MSIL (Microsoft Intermediate Language) precedente all'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="fbf3c-109">Nuovo offset MSIL relativo all'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="fbf3c-110">`true`se il mapping è noto per essere accurato; in `false`caso contrario, .</span><span class="sxs-lookup"><span data-stu-id="fbf3c-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fbf3c-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="fbf3c-111">Remarks</span></span>  
 <span data-ttu-id="fbf3c-112">Il formato della mappa è il seguente: `oldOffset` il debugger presupporrà che fa riferimento a un offset MSIL all'interno del codice MSIL originale non modificato.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="fbf3c-113">Il `newOffset` parametro si riferisce all'offset MSIL corrispondente all'interno del nuovo codice instrumentato.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="fbf3c-114">Affinché il passaggio funzioni correttamente, è necessario che siano soddisfatti i seguenti requisiti:</span><span class="sxs-lookup"><span data-stu-id="fbf3c-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="fbf3c-115">La mappa deve essere ordinata in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="fbf3c-116">Il codice MSIL instrumentato non deve essere riordinato.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="fbf3c-117">Il codice MSIL originale non deve essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="fbf3c-118">La mappa deve includere voci per eseguire il mapping di tutti i punti di sequenza dal file di database di programma (PDB).</span><span class="sxs-lookup"><span data-stu-id="fbf3c-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="fbf3c-119">La mappa non interpola le voci mancanti.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="fbf3c-120">Nell'esempio seguente viene illustrata una mappa e i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="fbf3c-121">Mappa:</span><span class="sxs-lookup"><span data-stu-id="fbf3c-121">Map:</span></span>  
  
- <span data-ttu-id="fbf3c-122">0 scostamento precedente, 0 nuovo offset</span><span class="sxs-lookup"><span data-stu-id="fbf3c-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="fbf3c-123">5 scostamento vecchio, 10 nuovi offset</span><span class="sxs-lookup"><span data-stu-id="fbf3c-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="fbf3c-124">9 vecchio offset, 20 nuovi offset</span><span class="sxs-lookup"><span data-stu-id="fbf3c-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="fbf3c-125">Risultati:</span><span class="sxs-lookup"><span data-stu-id="fbf3c-125">Results:</span></span>  
  
- <span data-ttu-id="fbf3c-126">Un offset precedente di 0, 1, 2, 3 o 4 verrà mappato a un nuovo offset pari a 0.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="fbf3c-127">Un offset precedente di 5, 6, 7 o 8 verrà mappato al nuovo offset 10.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="fbf3c-128">Un offset precedente di 9 o superiore verrà mappato al nuovo offset 20.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="fbf3c-129">Un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 verrà mappato all'offset precedente 0.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="fbf3c-130">Un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 verrà mappato all'offset 5.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="fbf3c-131">Un nuovo offset di 20 o superiore verrà mappato al vecchio offset 9.</span><span class="sxs-lookup"><span data-stu-id="fbf3c-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fbf3c-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fbf3c-132">Requirements</span></span>  
 <span data-ttu-id="fbf3c-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fbf3c-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf3c-134">**Intestazione:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="fbf3c-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="fbf3c-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fbf3c-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fbf3c-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbf3c-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf3c-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fbf3c-137">See also</span></span>

- [<span data-ttu-id="fbf3c-138">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="fbf3c-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="fbf3c-139">Debug</span><span class="sxs-lookup"><span data-stu-id="fbf3c-139">Debugging</span></span>](index.md)
