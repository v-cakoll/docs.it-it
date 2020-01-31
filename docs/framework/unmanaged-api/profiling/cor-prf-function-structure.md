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
ms.openlocfilehash: 14dcb251e25b5bd502c8d514a6dc35778fbe9f73
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867230"
---
# <a name="cor_prf_function-structure"></a><span data-ttu-id="2cc6b-102">Struttura COR_PRF_FUNCTION</span><span class="sxs-lookup"><span data-stu-id="2cc6b-102">COR_PRF_FUNCTION Structure</span></span>
<span data-ttu-id="2cc6b-103">Fornisce una rappresentazione univoca di una funzione combinando il relativo ID con l'ID della versione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="2cc6b-103">Provides a unique representation of a function by combining its ID with the ID of its recompiled version.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2cc6b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2cc6b-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_PRF_FUNCTION {    FunctionID functionId;    ReJITID    reJitId;} COR_PRF_FUNCTION;  
```  
  
## <a name="members"></a><span data-ttu-id="2cc6b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2cc6b-105">Members</span></span>  
  
|<span data-ttu-id="2cc6b-106">Member</span><span class="sxs-lookup"><span data-stu-id="2cc6b-106">Member</span></span>|<span data-ttu-id="2cc6b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2cc6b-107">Description</span></span>|  
|------------|-----------------|  
|`functionId`|<span data-ttu-id="2cc6b-108">ID della funzione.</span><span class="sxs-lookup"><span data-stu-id="2cc6b-108">The ID of the function.</span></span>|  
|`reJitId`|<span data-ttu-id="2cc6b-109">ID della funzione ricompilata.</span><span class="sxs-lookup"><span data-stu-id="2cc6b-109">The ID of the recompiled function.</span></span> <span data-ttu-id="2cc6b-110">Il valore 0 (zero) rappresenta la versione originale della funzione.</span><span class="sxs-lookup"><span data-stu-id="2cc6b-110">A value of 0 (zero) represents the original version of the function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2cc6b-111">Note</span><span class="sxs-lookup"><span data-stu-id="2cc6b-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2cc6b-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2cc6b-112">Requirements</span></span>  
 <span data-ttu-id="2cc6b-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2cc6b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2cc6b-114">**Intestazione:** CorProf. idl</span><span class="sxs-lookup"><span data-stu-id="2cc6b-114">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2cc6b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2cc6b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2cc6b-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2cc6b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2cc6b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2cc6b-117">See also</span></span>

- [<span data-ttu-id="2cc6b-118">Strutture di profilatura</span><span class="sxs-lookup"><span data-stu-id="2cc6b-118">Profiling Structures</span></span>](profiling-structures.md)
