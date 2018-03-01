---
title: Struttura CLR_DEBUGGING_VERSION
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 092024f3f4e6fc1bc923ae2a299c5d9c21f1b1b8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="clrdebuggingversion-structure"></a><span data-ttu-id="2135a-102">Struttura CLR_DEBUGGING_VERSION</span><span class="sxs-lookup"><span data-stu-id="2135a-102">CLR_DEBUGGING_VERSION Structure</span></span>
<span data-ttu-id="2135a-103">Definisce la versione del prodotto di Common Language Runtime (CLR) per fini di debug.</span><span class="sxs-lookup"><span data-stu-id="2135a-103">Defines the product version of the common language runtime (CLR) for debugging purposes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2135a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2135a-104">Syntax</span></span>  
  
```  
Typedef struct _CLR_DEBUGGING_VERSION  
{  
WORD wStructVersion;  
WORD wMajor;   
WORD wMinor;  
WORD wBuild;  
WORD wRevision;  
}  CLR_DEBUGGING_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="2135a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2135a-105">Members</span></span>  
  
|<span data-ttu-id="2135a-106">Membro</span><span class="sxs-lookup"><span data-stu-id="2135a-106">Member</span></span>|<span data-ttu-id="2135a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2135a-107">Description</span></span>|  
|------------|-----------------|  
|`wStructVersion`|<span data-ttu-id="2135a-108">Il numero di versione della struttura</span><span class="sxs-lookup"><span data-stu-id="2135a-108">The structure version number</span></span>|  
|`wMajor`|<span data-ttu-id="2135a-109">Numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="2135a-109">The major version number.</span></span>|  
|`wMinor`|<span data-ttu-id="2135a-110">Numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="2135a-110">The minor version number.</span></span>|  
|`wBuild`|<span data-ttu-id="2135a-111">Il numero di build.</span><span class="sxs-lookup"><span data-stu-id="2135a-111">The build number.</span></span>|  
|`wRevision`|<span data-ttu-id="2135a-112">Il numero di revisione.</span><span class="sxs-lookup"><span data-stu-id="2135a-112">The revision number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2135a-113">Note</span><span class="sxs-lookup"><span data-stu-id="2135a-113">Remarks</span></span>  
 <span data-ttu-id="2135a-114">Il `CLR_DEBUGGING_VERSION` struttura è identica alla struttura COR_VERSION, tuttavia, il `CLR_DEBUGGING_VERSION` struttura fornisce un campo di versione della struttura aggiuntiva (`wStructVersion`).</span><span class="sxs-lookup"><span data-stu-id="2135a-114">The `CLR_DEBUGGING_VERSION` structure is the same as the COR_VERSION structure, however, the `CLR_DEBUGGING_VERSION` structure provides an additional structure version field (`wStructVersion`).</span></span> <span data-ttu-id="2135a-115">Attualmente questo campo deve essere impostato su zero.</span><span class="sxs-lookup"><span data-stu-id="2135a-115">Currently, this field must be set to zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2135a-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2135a-116">Requirements</span></span>  
 <span data-ttu-id="2135a-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2135a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2135a-118">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="2135a-118">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="2135a-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2135a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2135a-120">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2135a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2135a-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2135a-121">See Also</span></span>  
 [<span data-ttu-id="2135a-122">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="2135a-122">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="2135a-123">Debug</span><span class="sxs-lookup"><span data-stu-id="2135a-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
