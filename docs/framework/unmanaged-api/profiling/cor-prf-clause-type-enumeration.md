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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 18197f0c500a205a66bdda8a9401f31d4208ae67
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780437"
---
# <a name="corprfclausetype-enumeration"></a><span data-ttu-id="281fb-102">Enumerazione COR_PRF_CLAUSE_TYPE</span><span class="sxs-lookup"><span data-stu-id="281fb-102">COR_PRF_CLAUSE_TYPE Enumeration</span></span>
<span data-ttu-id="281fb-103">Indica il tipo di clausola di eccezione in cui il codice è appena entrato o da cui è appena uscito.</span><span class="sxs-lookup"><span data-stu-id="281fb-103">Indicates the type of exception clause that the code has just entered or left.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="281fb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="281fb-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_CLAUSE_NONE = 0,  
    COR_PRF_CLAUSE_FILTER = 1,  
    COR_PRF_CLAUSE_CATCH = 2,  
    COR_PRF_CLAUSE_FINALLY = 3,  
} COR_PRF_CLAUSE_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="281fb-105">Membri</span><span class="sxs-lookup"><span data-stu-id="281fb-105">Members</span></span>  
  
|<span data-ttu-id="281fb-106">Member</span><span class="sxs-lookup"><span data-stu-id="281fb-106">Member</span></span>|<span data-ttu-id="281fb-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="281fb-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_CLAUSE_NONE`|<span data-ttu-id="281fb-108">La clausola di eccezione non è valida.</span><span class="sxs-lookup"><span data-stu-id="281fb-108">The exception clause is not valid.</span></span>|  
|`COR_PRF_CLAUSE_FILTER`|<span data-ttu-id="281fb-109">La clausola di eccezione è un'espressione di filtro.</span><span class="sxs-lookup"><span data-stu-id="281fb-109">The exception clause is a filter expression.</span></span>|  
|`COR_PRF_CLAUSE_CATCH`|<span data-ttu-id="281fb-110">La clausola di eccezione è un `catch` istruzione.</span><span class="sxs-lookup"><span data-stu-id="281fb-110">The exception clause is a `catch` statement.</span></span>|  
|`COR_PRF_CLAUSE_FINALLY`|<span data-ttu-id="281fb-111">La clausola di eccezione è un `finally` istruzione.</span><span class="sxs-lookup"><span data-stu-id="281fb-111">The exception clause is a `finally` statement.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="281fb-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="281fb-112">Requirements</span></span>  
 <span data-ttu-id="281fb-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="281fb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="281fb-114">**Intestazione:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="281fb-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="281fb-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="281fb-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="281fb-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="281fb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="281fb-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="281fb-117">See also</span></span>

- [<span data-ttu-id="281fb-118">Enumerazioni di profilatura</span><span class="sxs-lookup"><span data-stu-id="281fb-118">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
