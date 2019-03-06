---
title: Enumerazione CorDebugGCType
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fe8be6a7c18fff54825f981672f0f640bb60c35c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57482210"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="51891-102">Enumerazione CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="51891-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="51891-103">Indica se un Garbage Collector è in esecuzione in una workstation o in un server.</span><span class="sxs-lookup"><span data-stu-id="51891-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51891-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51891-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="51891-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="51891-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="51891-106">Membri</span><span class="sxs-lookup"><span data-stu-id="51891-106">Members</span></span>  
  
|<span data-ttu-id="51891-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="51891-107">Member name</span></span>|<span data-ttu-id="51891-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51891-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="51891-109">Il garbage collector è in esecuzione in una workstation.</span><span class="sxs-lookup"><span data-stu-id="51891-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="51891-110">Il garbage collector è in esecuzione in un server.</span><span class="sxs-lookup"><span data-stu-id="51891-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51891-111">Note</span><span class="sxs-lookup"><span data-stu-id="51891-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51891-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51891-112">Requirements</span></span>  
 <span data-ttu-id="51891-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51891-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51891-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="51891-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="51891-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51891-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51891-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51891-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51891-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51891-117">See also</span></span>
- [<span data-ttu-id="51891-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="51891-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
