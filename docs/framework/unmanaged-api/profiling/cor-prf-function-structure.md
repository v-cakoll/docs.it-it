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
ms.openlocfilehash: 856e01c7934709a17556aa53851204bf6a917de8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500936"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="105cc-102">Struttura COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="105cc-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="105cc-103">Fornisce una rappresentazione univoca di una funzione combinando il relativo ID con l'ID della versione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="105cc-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="105cc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="105cc-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="105cc-105">Membri</span><span class="sxs-lookup"><span data-stu-id="105cc-105">Members</span></span>  
  
|<span data-ttu-id="105cc-106">Membro</span><span class="sxs-lookup"><span data-stu-id="105cc-106">Member</span></span>|<span data-ttu-id="105cc-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="105cc-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="105cc-108">ID della funzione.</span><span class="sxs-lookup"><span data-stu-id="105cc-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="105cc-109">ID della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="105cc-109">The ID of the recompiled function.</span></span> <span data-ttu-id="105cc-110">Il valore 0 (zero) rappresenta la versione originale della funzione.</span><span class="sxs-lookup"><span data-stu-id="105cc-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="105cc-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="105cc-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="105cc-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="105cc-112">Requirements</span></span>  
 <span data-ttu-id="105cc-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="105cc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="105cc-114">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="105cc-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="105cc-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="105cc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="105cc-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="105cc-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="105cc-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="105cc-117">See also</span></span>

- [<span data-ttu-id="105cc-118">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="105cc-118">Profiling Structures</span></span>](profiling-structures.md)
