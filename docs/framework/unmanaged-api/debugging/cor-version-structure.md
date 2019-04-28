---
title: Struttura COR_VERSION
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 00e58d83c19c3cb6a2e1eb38942500d7f5dc5cf9
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609295"
---
# <a name="corversion-structure"></a><span data-ttu-id="20c67-102">Struttura COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="20c67-102">COR_VERSION Structure</span></span>
<span data-ttu-id="20c67-103">Archivia il numero di versione in quattro parti standard di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="20c67-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20c67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="20c67-104">Syntax</span></span>  
  
```  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="20c67-105">Membri</span><span class="sxs-lookup"><span data-stu-id="20c67-105">Members</span></span>  
  
|<span data-ttu-id="20c67-106">Member</span><span class="sxs-lookup"><span data-stu-id="20c67-106">Member</span></span>|<span data-ttu-id="20c67-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="20c67-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="20c67-108">Numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="20c67-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="20c67-109">Numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="20c67-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="20c67-110">Il numero di build.</span><span class="sxs-lookup"><span data-stu-id="20c67-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="20c67-111">Il numero di build secondaria.</span><span class="sxs-lookup"><span data-stu-id="20c67-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="20c67-112">Note</span><span class="sxs-lookup"><span data-stu-id="20c67-112">Remarks</span></span>  
 <span data-ttu-id="20c67-113">Se il numero di versione è 1.0.3705.288, il numero di versione principale è 1, 0 è il numero di versione secondaria, 3705 è il numero di build e 288 è il numero di build secondaria.</span><span class="sxs-lookup"><span data-stu-id="20c67-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20c67-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="20c67-114">Requirements</span></span>  
 <span data-ttu-id="20c67-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20c67-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20c67-116">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="20c67-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="20c67-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20c67-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20c67-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20c67-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20c67-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="20c67-119">See also</span></span>

- [<span data-ttu-id="20c67-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="20c67-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="20c67-121">Debug</span><span class="sxs-lookup"><span data-stu-id="20c67-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
