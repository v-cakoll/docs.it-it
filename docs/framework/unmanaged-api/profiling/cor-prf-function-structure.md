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
ms.openlocfilehash: 098aaca8ec318b08c87e30c2a9558b7e64494a4c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582002"
---
# <a name="corprffunction-structure"></a><span data-ttu-id="ce872-102">Struttura COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="ce872-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="ce872-103">Fornisce una rappresentazione univoca di una funzione combinando il relativo ID con l'ID della versione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="ce872-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce872-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ce872-104">Syntax</span></span>  
  
```  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="ce872-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ce872-105">Members</span></span>  
  
|<span data-ttu-id="ce872-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ce872-106">Member</span></span>|<span data-ttu-id="ce872-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ce872-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="ce872-108">L'ID della funzione.</span><span class="sxs-lookup"><span data-stu-id="ce872-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="ce872-109">L'ID della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="ce872-109">The ID of the recompiled function.</span></span> <span data-ttu-id="ce872-110">Un valore pari a 0 (zero) rappresenta la versione originale della funzione.</span><span class="sxs-lookup"><span data-stu-id="ce872-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce872-111">Note</span><span class="sxs-lookup"><span data-stu-id="ce872-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce872-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ce872-112">Requirements</span></span>  
 <span data-ttu-id="ce872-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce872-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce872-114">**Intestazione:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="ce872-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="ce872-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce872-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce872-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce872-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce872-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ce872-117">See also</span></span>
- [<span data-ttu-id="ce872-118">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="ce872-118">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
