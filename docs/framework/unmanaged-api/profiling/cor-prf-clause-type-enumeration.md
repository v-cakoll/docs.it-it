---
title: Enumerazione COR_PRF_CLAUSE_TYPE
ms.date: 03/30/2017
api_name:
- COR_PRF_CLAUSE_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_CLAUSE_TYPE
helpviewer_keywords:
- COR_PRF_CLAUSE_TYPE enumeration [.NET Framework profiling]
ms.assetid: f64c325a-ed3a-4aaf-b847-a88edbc4fefc
topic_type:
- apiref
ms.openlocfilehash: a308017dc80dd973cbf108ba9df824193775f5ff
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501053"
---
# <a name="cor_prf_clause_type-enumeration"></a><span data-ttu-id="5a0bd-102">Enumerazione COR_PRF_CLAUSE_TYPE</span><span class="sxs-lookup"><span data-stu-id="5a0bd-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="5a0bd-103">Indica il tipo di clausola di eccezione in cui il codice è appena entrato o da cui è appena uscito.</span><span class="sxs-lookup"><span data-stu-id="5a0bd-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a0bd-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5a0bd-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="5a0bd-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5a0bd-105">Members</span></span>  
  
|<span data-ttu-id="5a0bd-106">Membro</span><span class="sxs-lookup"><span data-stu-id="5a0bd-106">Member</span></span>|<span data-ttu-id="5a0bd-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5a0bd-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="5a0bd-108">Clausola Exception non valida.</span><span class="sxs-lookup"><span data-stu-id="5a0bd-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="5a0bd-109">La clausola Exception è un'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="5a0bd-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="5a0bd-110">La clausola Exception è un' `catch` istruzione.</span><span class="sxs-lookup"><span data-stu-id="5a0bd-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="5a0bd-111">La clausola Exception è un' `finally` istruzione.</span><span class="sxs-lookup"><span data-stu-id="5a0bd-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5a0bd-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5a0bd-112">Requirements</span></span>  
 <span data-ttu-id="5a0bd-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a0bd-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a0bd-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a0bd-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a0bd-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a0bd-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a0bd-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a0bd-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0bd-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5a0bd-117">See also</span></span>

- [<span data-ttu-id="5a0bd-118">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="5a0bd-118">Profiling Enumerations</span></span>](profiling-enumerations.md)
