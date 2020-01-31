---
title: Struttura CorDebugEHClause
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugEHClause
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 0e350a1b-6997-46d0-bfc5-962a5011ef43
topic_type:
- apiref
ms.openlocfilehash: 197c33511a474eb8291e4361ebb3c21fb3720cae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789420"
---
# <a name="cordebugehclause-structure"></a><span data-ttu-id="641fe-102">Struttura CorDebugEHClause</span><span class="sxs-lookup"><span data-stu-id="641fe-102">CorDebugEHClause Structure</span></span>
<span data-ttu-id="641fe-103">[Supportato in .NET Framework 4.5.2 e versioni successive]</span><span class="sxs-lookup"><span data-stu-id="641fe-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="641fe-104">Rappresenta una clausola di gestione delle eccezioni (EH, Exception Handling) per una determinata parte di codice del linguaggio intermedio (IL, Intermediate Language).</span><span class="sxs-lookup"><span data-stu-id="641fe-104">Represents an exception handling (EH) clause for a given piece of intermediate language (IL) code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="641fe-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="641fe-105">Syntax</span></span>  
  
```cpp
typedef struct _CorDebugEHClause {  
   ULONG32 Flags;  
   ULONG32 TryOffset;  
   ULONG32 TryLength;  
   ULONG32 HandlerOffset;  
   ULONG32 HandlerLength;  
   ULONG32 ClassToken;  
   ULONG32 FilterOffset;  
} CorDebugEHClause;  
```  
  
## <a name="members"></a><span data-ttu-id="641fe-106">Membri</span><span class="sxs-lookup"><span data-stu-id="641fe-106">Members</span></span>  
  
|<span data-ttu-id="641fe-107">Member</span><span class="sxs-lookup"><span data-stu-id="641fe-107">Member</span></span>|<span data-ttu-id="641fe-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="641fe-108">Description</span></span>|  
|------------|-----------------|  
|`Flags`|<span data-ttu-id="641fe-109">Campo di bit che descrive le informazioni sull'eccezione nella clausola di gestione delle eccezioni.</span><span class="sxs-lookup"><span data-stu-id="641fe-109">A bit field that describes the exception information in the EH clause.</span></span> <span data-ttu-id="641fe-110">Per altre informazioni, vedere la sezione Osservazioni.</span><span class="sxs-lookup"><span data-stu-id="641fe-110">For more information, see the Remarks section.</span></span>|  
|`TryOffset`|<span data-ttu-id="641fe-111">Offset, in byte, del blocco `try` dall'inizio del corpo del metodo.</span><span class="sxs-lookup"><span data-stu-id="641fe-111">The offset, in bytes, of the `try` block from the start of the method body.</span></span>|  
|`TryLength`|<span data-ttu-id="641fe-112">Lunghezza in byte del blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="641fe-112">The length, in bytes, of the `try` block.</span></span>|  
|`HandlerOffset`|<span data-ttu-id="641fe-113">Il percorso del gestore per questo blocco `try`.</span><span class="sxs-lookup"><span data-stu-id="641fe-113">The location of the handler for this `try` block.</span></span>|  
|`HandlerLength`|<span data-ttu-id="641fe-114">Le dimensioni in byte del codice del gestore.</span><span class="sxs-lookup"><span data-stu-id="641fe-114">The size of the handler code in bytes.</span></span>|  
|`ClassToken`|<span data-ttu-id="641fe-115">Il token dei metadati per un gestore di eccezioni basato sul tipo.</span><span class="sxs-lookup"><span data-stu-id="641fe-115">The metadata token for a type-based exception handler.</span></span>|  
|`FilterOffset`|<span data-ttu-id="641fe-116">Offset, in byte, dall'inizio del corpo del metodo per un gestore di eccezioni basato sul filtro.</span><span class="sxs-lookup"><span data-stu-id="641fe-116">The offset, in bytes, from the start of the method body for a filter-based exception handler.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="641fe-117">Note</span><span class="sxs-lookup"><span data-stu-id="641fe-117">Remarks</span></span>  
 <span data-ttu-id="641fe-118">Una matrice di valori `CoreDebugEHClause` viene restituita dal metodo [GetEHClauses](icordebugilcode-getehclauses-method.md) .</span><span class="sxs-lookup"><span data-stu-id="641fe-118">An array of `CoreDebugEHClause` values is returned by the [GetEHClauses](icordebugilcode-getehclauses-method.md) method.</span></span>  
  
 <span data-ttu-id="641fe-119">Le informazioni sulla clausola di gestione delle eccezioni sono definite dalla specifica CLI.</span><span class="sxs-lookup"><span data-stu-id="641fe-119">The EH clause information is defined by the CLI specification.</span></span> <span data-ttu-id="641fe-120">Per ulteriori informazioni, vedere [standard ECMA-355: Common Language Infrastructure (CLI), 6a Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span><span class="sxs-lookup"><span data-stu-id="641fe-120">For more information, see [Standard ECMA-355: Common Language Infrastructure (CLI), 6th Edition](https://www.ecma-international.org/publications/standards/Ecma-335.htm).</span></span>  
  
 <span data-ttu-id="641fe-121">Il campo `flags` può contenere i flag seguenti.</span><span class="sxs-lookup"><span data-stu-id="641fe-121">The `flags` field can contain the following flags.</span></span> <span data-ttu-id="641fe-122">Si noti che non sono definiti in CorDebug.idl o CorDebug.h.</span><span class="sxs-lookup"><span data-stu-id="641fe-122">Note that they are not defined in CorDebug.idl or CorDebug.h.</span></span>  
  
|<span data-ttu-id="641fe-123">Flag</span><span class="sxs-lookup"><span data-stu-id="641fe-123">Flag</span></span>|<span data-ttu-id="641fe-124">Valore</span><span class="sxs-lookup"><span data-stu-id="641fe-124">Value</span></span>|<span data-ttu-id="641fe-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="641fe-125">Description</span></span>|  
|----------|-----------|-----------------|  
|`COR_ILEXCEPTION_CLAUSE_EXCEPTION`|<span data-ttu-id="641fe-126">0x00000000</span><span class="sxs-lookup"><span data-stu-id="641fe-126">0x00000000</span></span>|<span data-ttu-id="641fe-127">Clausola dell'eccezione tipizzata.</span><span class="sxs-lookup"><span data-stu-id="641fe-127">A typed exception clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FILTER`|<span data-ttu-id="641fe-128">0x00000001</span><span class="sxs-lookup"><span data-stu-id="641fe-128">0x00000001</span></span>|<span data-ttu-id="641fe-129">Clausola del gestore e del filtro eccezioni.</span><span class="sxs-lookup"><span data-stu-id="641fe-129">An exception filter and handler clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FINALLY`|<span data-ttu-id="641fe-130">0x00000002</span><span class="sxs-lookup"><span data-stu-id="641fe-130">0x00000002</span></span>|<span data-ttu-id="641fe-131">Clausola `finally`.</span><span class="sxs-lookup"><span data-stu-id="641fe-131">A `finally` clause.</span></span>|  
|`COR_ILEXCEPTION_CLAUSE_FAULT`|<span data-ttu-id="641fe-132">0x00000004</span><span class="sxs-lookup"><span data-stu-id="641fe-132">0x00000004</span></span>|<span data-ttu-id="641fe-133">Clausola fault (una clausola `finally` che viene chiamata solo quando viene generata un'eccezione).</span><span class="sxs-lookup"><span data-stu-id="641fe-133">A fault clause (a `finally` clause that is called only when an exception is thrown).</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="641fe-134">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="641fe-134">Requirements</span></span>  
 <span data-ttu-id="641fe-135">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="641fe-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="641fe-136">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="641fe-136">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="641fe-137">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="641fe-137">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="641fe-138">**Versioni .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="641fe-138">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="641fe-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="641fe-139">See also</span></span>

- [<span data-ttu-id="641fe-140">Metodo GetEHClauses</span><span class="sxs-lookup"><span data-stu-id="641fe-140">GetEHClauses Method</span></span>](icordebugilcode-getehclauses-method.md)
- [<span data-ttu-id="641fe-141">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="641fe-141">Debugging Structures</span></span>](debugging-structures.md)
