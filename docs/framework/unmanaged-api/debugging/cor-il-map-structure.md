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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c7452b76509d5eca592cc3b95df1f77703ec1111
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54561829"
---
# <a name="corilmap-structure"></a><span data-ttu-id="9cc88-102">Struttura COR_IL_MAP</span><span class="sxs-lookup"><span data-stu-id="9cc88-102">COR_IL_MAP Structure</span></span>
<span data-ttu-id="9cc88-103">Specifica le modifiche nell'offset relativo di una funzione.</span><span class="sxs-lookup"><span data-stu-id="9cc88-103">Specifies changes in the relative offset of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9cc88-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9cc88-104">Syntax</span></span>  
  
```  
typedef struct _COR_IL_MAP {  
    ULONG32 oldOffset;   
    ULONG32 newOffset;   
    BOOL    fAccurate;  
} COR_IL_MAP;  
```  
  
## <a name="members"></a><span data-ttu-id="9cc88-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9cc88-105">Members</span></span>  
  
|<span data-ttu-id="9cc88-106">Membro</span><span class="sxs-lookup"><span data-stu-id="9cc88-106">Member</span></span>|<span data-ttu-id="9cc88-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9cc88-107">Description</span></span>|  
|------------|-----------------|  
|`oldOffset`|<span data-ttu-id="9cc88-108">Il vecchio offset Microsoft intermediate language (MSIL) relativo all'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="9cc88-108">The old Microsoft intermediate language (MSIL) offset relative to the beginning of the function.</span></span>|  
|`newOffset`|<span data-ttu-id="9cc88-109">L'offset MSIL nuovo rispetto all'inizio della funzione.</span><span class="sxs-lookup"><span data-stu-id="9cc88-109">The new MSIL offset relative to the beginning of the function.</span></span>|  
|`fAccurate`|<span data-ttu-id="9cc88-110">`true` Se il mapping è nota l'accuratezza; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="9cc88-110">`true` if the mapping is known to be accurate; otherwise, `false`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9cc88-111">Note</span><span class="sxs-lookup"><span data-stu-id="9cc88-111">Remarks</span></span>  
 <span data-ttu-id="9cc88-112">Il formato della mappa è come segue: Il debugger presupporrà che `oldOffset` fa riferimento a un offset MSIL all'interno del codice MSIL originale, non modificato.</span><span class="sxs-lookup"><span data-stu-id="9cc88-112">The format of the map is as follows: The debugger will assume that `oldOffset` refers to an MSIL offset within the original, unmodified MSIL code.</span></span> <span data-ttu-id="9cc88-113">Il `newOffset` parametro fa riferimento all'offset MSIL corrispondente all'interno del nuovo codice instrumentato.</span><span class="sxs-lookup"><span data-stu-id="9cc88-113">The `newOffset` parameter refers to the corresponding MSIL offset within the new, instrumented code.</span></span>  
  
 <span data-ttu-id="9cc88-114">Per l'esecuzione di istruzioni per il corretto funzionamento, è necessario soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="9cc88-114">For stepping to work properly, the following requirements should be met:</span></span>  
  
-   <span data-ttu-id="9cc88-115">La mappa deve essere disposti in ordine crescente.</span><span class="sxs-lookup"><span data-stu-id="9cc88-115">The map should be sorted in ascending order.</span></span>  
  
-   <span data-ttu-id="9cc88-116">Il codice instrumentato MSIL non deve essere riordinato.</span><span class="sxs-lookup"><span data-stu-id="9cc88-116">Instrumented MSIL code should not be reordered.</span></span>  
  
-   <span data-ttu-id="9cc88-117">Il codice MSIL originale non deve essere rimossi.</span><span class="sxs-lookup"><span data-stu-id="9cc88-117">Original MSIL code should not be removed.</span></span>  
  
-   <span data-ttu-id="9cc88-118">La mappa deve includere le voci per eseguire il mapping di tutti i punti di sequenza dei file di database (PDB) di programma.</span><span class="sxs-lookup"><span data-stu-id="9cc88-118">The map should include entries to map all the sequence points from the program database (PDB) file.</span></span>  
  
 <span data-ttu-id="9cc88-119">La mappa non esegue l'interpolazione voci mancanti.</span><span class="sxs-lookup"><span data-stu-id="9cc88-119">The map does not interpolate missing entries.</span></span> <span data-ttu-id="9cc88-120">Nell'esempio seguente viene illustrata una mappa e i relativi risultati.</span><span class="sxs-lookup"><span data-stu-id="9cc88-120">The following example shows a map and its results.</span></span>  
  
 <span data-ttu-id="9cc88-121">Eseguire il mapping:</span><span class="sxs-lookup"><span data-stu-id="9cc88-121">Map:</span></span>  
  
-   <span data-ttu-id="9cc88-122">vecchio offset 0, 0 nuovo offset</span><span class="sxs-lookup"><span data-stu-id="9cc88-122">0 old offset, 0 new offset</span></span>  
  
-   <span data-ttu-id="9cc88-123">offset precedente 5, 10 nuovo offset</span><span class="sxs-lookup"><span data-stu-id="9cc88-123">5 old offset, 10 new offset</span></span>  
  
-   <span data-ttu-id="9cc88-124">offset precedente 9, 20 nuovo offset</span><span class="sxs-lookup"><span data-stu-id="9cc88-124">9 old offset, 20 new offset</span></span>  
  
 <span data-ttu-id="9cc88-125">Risultati:</span><span class="sxs-lookup"><span data-stu-id="9cc88-125">Results:</span></span>  
  
-   <span data-ttu-id="9cc88-126">Un offset 0, 1, 2, 3 o 4 precedente verrà mappato a un nuovo offset pari a 0.</span><span class="sxs-lookup"><span data-stu-id="9cc88-126">An old offset of 0, 1, 2, 3, or 4 will be mapped to a new offset of 0.</span></span>  
  
-   <span data-ttu-id="9cc88-127">Verrà eseguito il mapping di un offset precedente del 5, 6, 7 o 8 al nuovo offset 10.</span><span class="sxs-lookup"><span data-stu-id="9cc88-127">An old offset of 5, 6, 7, or 8 will be mapped to new offset 10.</span></span>  
  
-   <span data-ttu-id="9cc88-128">Verrà eseguito il mapping di un offset precedente del 9 o versione successiva al nuovo offset 20.</span><span class="sxs-lookup"><span data-stu-id="9cc88-128">An old offset of 9 or higher will be mapped to new offset 20.</span></span>  
  
-   <span data-ttu-id="9cc88-129">Verrà eseguito il mapping di un nuovo offset 0, 1, 2, 3, 4, 5, 6, 7, 8 o 9 al vecchio offset 0.</span><span class="sxs-lookup"><span data-stu-id="9cc88-129">A new offset of 0, 1, 2, 3, 4, 5, 6, 7, 8, or 9 will be mapped to old offset 0.</span></span>  
  
-   <span data-ttu-id="9cc88-130">Verrà eseguito il mapping di un nuovo offset di 10, 11, 12, 13, 14, 15, 16, 17, 18 o 19 al vecchio offset 5.</span><span class="sxs-lookup"><span data-stu-id="9cc88-130">A new offset of 10, 11, 12, 13, 14, 15, 16, 17, 18, or 19 will be mapped to old offset 5.</span></span>  
  
-   <span data-ttu-id="9cc88-131">Verrà eseguito il mapping di un nuovo offset pari a 20 o superiore al vecchio offset 9.</span><span class="sxs-lookup"><span data-stu-id="9cc88-131">A new offset of 20 or higher will be mapped to old offset 9.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9cc88-132">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9cc88-132">Requirements</span></span>  
 <span data-ttu-id="9cc88-133">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9cc88-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9cc88-134">**Intestazione:** CorDebug.idl, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="9cc88-134">**Header:** CorDebug.idl, CorProf.idl</span></span>  
  
 <span data-ttu-id="9cc88-135">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9cc88-135">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9cc88-136">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9cc88-136">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9cc88-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9cc88-137">See also</span></span>
- [<span data-ttu-id="9cc88-138">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="9cc88-138">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="9cc88-139">Debug</span><span class="sxs-lookup"><span data-stu-id="9cc88-139">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
