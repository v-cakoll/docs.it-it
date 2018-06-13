---
title: Enumerazione COR_PUB_ENUMPROCESS
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fcdb5883e109d7e0c73c8fb76ee61b52cf23091f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407001"
---
# <a name="corpubenumprocess-enumeration"></a><span data-ttu-id="8cf18-102">Enumerazione COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="8cf18-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="8cf18-103">Identifica il tipo di processo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="8cf18-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cf18-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8cf18-104">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="8cf18-105">Membri</span><span class="sxs-lookup"><span data-stu-id="8cf18-105">Members</span></span>  
  
|<span data-ttu-id="8cf18-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="8cf18-106">Member name</span></span>|<span data-ttu-id="8cf18-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8cf18-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="8cf18-108">Un processo gestito.</span><span class="sxs-lookup"><span data-stu-id="8cf18-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8cf18-109">Note</span><span class="sxs-lookup"><span data-stu-id="8cf18-109">Remarks</span></span>  
 <span data-ttu-id="8cf18-110">La versione corrente dell'API di debug non gestito enumera solo i processi gestiti.</span><span class="sxs-lookup"><span data-stu-id="8cf18-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cf18-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8cf18-111">Requirements</span></span>  
 <span data-ttu-id="8cf18-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cf18-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cf18-113">**Intestazione:** Corpub. idl, CorPub.h</span><span class="sxs-lookup"><span data-stu-id="8cf18-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="8cf18-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="8cf18-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8cf18-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cf18-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cf18-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8cf18-116">See Also</span></span>  
 [<span data-ttu-id="8cf18-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="8cf18-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
