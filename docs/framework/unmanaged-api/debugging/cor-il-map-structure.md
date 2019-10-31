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
ms.openlocfilehash: c37f039d9636854c464e7981693c573bd60deab9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132348"
---
# <a name="cor_il_map-structure"></a><span data-ttu-id="3e609-102">Struttura COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="3e609-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="3e609-103">Specifica le modifiche nell'offset relativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="3e609-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e609-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3e609-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="3e609-105">Members</span><span class="sxs-lookup"><span data-stu-id="3e609-105">Members</span></span>  
  
|<span data-ttu-id="3e609-106">Member</span><span class="sxs-lookup"><span data-stu-id="3e609-106">Member</span></span>|<span data-ttu-id="3e609-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3e609-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="3e609-108">Offset MSIL (Microsoft Intermediate Language) precedente relativo all'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="3e609-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="3e609-109">Nuovo offset MSIL relativo all'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="3e609-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="3e609-110">`true` se il mapping è noto come accurato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3e609-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3e609-111">Note</span><span class="sxs-lookup"><span data-stu-id="3e609-111">Remarks</span></span>  
 <span data-ttu-id="3e609-112">Il formato della mappa è il seguente: il debugger presuppone che `oldOffset` faccia riferimento a un offset MSIL all'interno del codice MSIL originale, non modificato.</span><span class="sxs-lookup"><span data-stu-id="3e609-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="3e609-113">Il parametro `newOffset` si riferisce all'offset MSIL corrispondente all'interno del nuovo codice instrumentato.</span><span class="sxs-lookup"><span data-stu-id="3e609-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="3e609-114">Per il corretto funzionamento, è necessario soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="3e609-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
- <span data-ttu-id="3e609-115">La mappa deve essere ordinata in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="3e609-115">The map should be sorted in ascending order.</span></span>  
  
- <span data-ttu-id="3e609-116">Il codice MSIL instrumentato non deve essere riordinato.</span><span class="sxs-lookup"><span data-stu-id="3e609-116">Instrumented MSIL code should not be reordered.</span></span>  
  
- <span data-ttu-id="3e609-117">Il codice MSIL originale non deve essere rimosso.</span><span class="sxs-lookup"><span data-stu-id="3e609-117">Original MSIL code should not be removed.</span></span>  
  
- <span data-ttu-id="3e609-118">La mappa deve includere le voci per eseguire il mapping di tutti i punti di sequenza dal file di database di programma (PDB).</span><span class="sxs-lookup"><span data-stu-id="3e609-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="3e609-119">La mappa non esegue l'interpolazione delle voci mancanti.</span><span class="sxs-lookup"><span data-stu-id="3e609-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="3e609-120">Nell'esempio seguente viene illustrata una mappa e i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="3e609-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="3e609-121">Mappa</span><span class="sxs-lookup"><span data-stu-id="3e609-121">Map:</span></span>  
  
- <span data-ttu-id="3e609-122">0 offset precedente, 0 nuovo offset</span><span class="sxs-lookup"><span data-stu-id="3e609-122">0 old offset, 0 new offset</span></span>  
  
- <span data-ttu-id="3e609-123">5 offset precedente, 10 nuovo offset</span><span class="sxs-lookup"><span data-stu-id="3e609-123">5 old offset, 10 new offset</span></span>  
  
- <span data-ttu-id="3e609-124">9 offset precedente, 20 nuovo offset</span><span class="sxs-lookup"><span data-stu-id="3e609-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="3e609-125">Risultati</span><span class="sxs-lookup"><span data-stu-id="3e609-125">Results:</span></span>  
  
- <span data-ttu-id="3e609-126">Un offset precedente di 0, 1, 2, 3 o 4 verrà mappato a un nuovo offset di 0.</span><span class="sxs-lookup"><span data-stu-id="3e609-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
- <span data-ttu-id="3e609-127">Viene eseguito il mapping di un offset precedente di 5, 6, 7 o 8 al nuovo offset 10.</span><span class="sxs-lookup"><span data-stu-id="3e609-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
- <span data-ttu-id="3e609-128">Verrà eseguito il mapping di un offset precedente di 9 o superiore al nuovo offset 20.</span><span class="sxs-lookup"><span data-stu-id="3e609-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
- <span data-ttu-id="3e609-129">Viene eseguito il mapping di un nuovo offset di 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 all'offset precedente 0.</span><span class="sxs-lookup"><span data-stu-id="3e609-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
- <span data-ttu-id="3e609-130">Viene eseguito il mapping di un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 alla precedente offset 5.</span><span class="sxs-lookup"><span data-stu-id="3e609-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
- <span data-ttu-id="3e609-131">Verrà eseguito il mapping di un nuovo offset di 20 o superiore alla precedente offset 9.</span><span class="sxs-lookup"><span data-stu-id="3e609-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e609-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3e609-132">Requirements</span></span>  
 <span data-ttu-id="3e609-133">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e609-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e609-134">**Intestazione:** CorDebug. idl, CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="3e609-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="3e609-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e609-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e609-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e609-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e609-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3e609-137">See also</span></span>

- [<span data-ttu-id="3e609-138">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="3e609-138">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="3e609-139">Debug</span><span class="sxs-lookup"><span data-stu-id="3e609-139">Debugging</span></span>](index.md)
