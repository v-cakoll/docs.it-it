---
title: Enumerazione CorDebugGCType
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
- CorDebugGCType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGCType
helpviewer_keywords:
- CorDebugGCType enumeration [.NET Framework debugging]
ms.assetid: 880ca92a-42d4-42a5-9b9c-c2848eb39c6a
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2045c2edd129c2e4154d24b43d96f6ea8ad64cab
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="cbb3e-102">Enumerazione CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="cbb3e-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="cbb3e-103">Indica se un Garbage Collector è in esecuzione in una workstation o in un server.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cbb3e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="cbb3e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cbb3e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="cbb3e-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="cbb3e-106">Membri</span><span class="sxs-lookup"><span data-stu-id="cbb3e-106">Members</span></span>  
  
|<span data-ttu-id="cbb3e-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="cbb3e-107">Member name</span></span>|<span data-ttu-id="cbb3e-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="cbb3e-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="cbb3e-109">Il garbage collector è in esecuzione in una workstation.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="cbb3e-110">Il garbage collector è in esecuzione in un server.</span><span class="sxs-lookup"><span data-stu-id="cbb3e-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cbb3e-111">Note</span><span class="sxs-lookup"><span data-stu-id="cbb3e-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cbb3e-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="cbb3e-112">Requirements</span></span>  
 <span data-ttu-id="cbb3e-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cbb3e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cbb3e-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="cbb3e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="cbb3e-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cbb3e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cbb3e-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cbb3e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbb3e-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cbb3e-117">See Also</span></span>  
 [<span data-ttu-id="cbb3e-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="cbb3e-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
