---
title: Struttura COR_PRF_FUNCTION
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION
helpviewer_keywords:
- COR_PRF_FUNCTION structure [.NET Framework profiling]
ms.assetid: 8bb5acf5-cf4b-4ccb-93f1-46db1f3f8bf3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1bc8d588641163ccf98054fdf1930a72a04c770c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452062"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="3735c-102">Struttura COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="3735c-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="3735c-103">Fornisce una rappresentazione univoca di una funzione combinando il relativo ID con l'ID della versione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="3735c-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3735c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3735c-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="3735c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3735c-105">Members</span></span>  
  
|<span data-ttu-id="3735c-106">Membro</span><span class="sxs-lookup"><span data-stu-id="3735c-106">Member</span></span>|<span data-ttu-id="3735c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3735c-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="3735c-108">L'ID della funzione.</span><span class="sxs-lookup"><span data-stu-id="3735c-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="3735c-109">L'ID della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="3735c-109">The ID of the recompiled function.</span></span> <span data-ttu-id="3735c-110">Un valore pari a 0 (zero) rappresenta la versione originale della funzione.</span><span class="sxs-lookup"><span data-stu-id="3735c-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3735c-111">Note</span><span class="sxs-lookup"><span data-stu-id="3735c-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3735c-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3735c-112">Requirements</span></span>  
 <span data-ttu-id="3735c-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3735c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3735c-114">**Intestazione:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="3735c-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="3735c-115">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="3735c-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3735c-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3735c-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3735c-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3735c-117">See Also</span></span>  
 [<span data-ttu-id="3735c-118">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="3735c-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
