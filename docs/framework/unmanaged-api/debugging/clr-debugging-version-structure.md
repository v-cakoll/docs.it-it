---
title: Struttura CLR_DEBUGGING_VERSION
ms.date: 03/30/2017
api_name:
- CLR_DEBUGGING_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_VERSION
helpviewer_keywords:
- CLR_DEBUGGING_VERSION structure [.NET Framework debugging]
ms.assetid: 4d821186-3ddf-405a-ac44-d79438a9f7f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4528ccd77fed2ea2a9b2d08243ffa1535bfad1ae
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274079"
---
# <a name="clr_debugging_version-structure"></a><span data-ttu-id="130e5-102">Struttura CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="130e5-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="130e5-103">Definisce la versione del prodotto di Common Language Runtime (CLR) per fini di debug.</span><span class="sxs-lookup"><span data-stu-id="130e5-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="130e5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="130e5-104">Syntax</span></span>  
  
```cpp  
typedef struct _CLR_DEBUGGING_VERSION  
{  
    WORD wStructVersion;
    WORD wMajor;
    WORD wMinor;
    WORD wBuild;
    WORD wRevision;
} CLR_DEBUGGING_VERSION;
```  
  
## <a name="members"></a><span data-ttu-id="130e5-105">Membri</span><span class="sxs-lookup"><span data-stu-id="130e5-105">Members</span></span>  
  
|<span data-ttu-id="130e5-106">Member</span><span class="sxs-lookup"><span data-stu-id="130e5-106">Member</span></span>|<span data-ttu-id="130e5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="130e5-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="130e5-108">Numero di versione della struttura</span><span class="sxs-lookup"><span data-stu-id="130e5-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="130e5-109">Numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="130e5-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="130e5-110">Numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="130e5-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="130e5-111">Numero di Build.</span><span class="sxs-lookup"><span data-stu-id="130e5-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="130e5-112">Numero di revisione.</span><span class="sxs-lookup"><span data-stu-id="130e5-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="130e5-113">Note</span><span class="sxs-lookup"><span data-stu-id="130e5-113">Remarks</span></span>  
 <span data-ttu-id="130e5-114">La `CLR_DEBUGGING_VERSION` struttura corrisponde alla struttura COR_VERSION, tuttavia, la `CLR_DEBUGGING_VERSION` struttura fornisce un campo della versione della struttura aggiuntiva (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="130e5-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="130e5-115">Attualmente, questo campo deve essere impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="130e5-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="130e5-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="130e5-116">Requirements</span></span>  
 <span data-ttu-id="130e5-117">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="130e5-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="130e5-118">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="130e5-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="130e5-119">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="130e5-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="130e5-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="130e5-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="130e5-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="130e5-121">See also</span></span>

- [<span data-ttu-id="130e5-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="130e5-122">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="130e5-123">Debug</span><span class="sxs-lookup"><span data-stu-id="130e5-123">Debugging</span></span>](index.md)
