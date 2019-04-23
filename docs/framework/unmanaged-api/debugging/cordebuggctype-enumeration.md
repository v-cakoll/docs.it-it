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
ms.openlocfilehash: 315d6dd522f3c6be2d36b1eb411d9f471350df60
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59182923"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="9d5f6-102">Enumerazione CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="9d5f6-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="9d5f6-103">Indica se un Garbage Collector è in esecuzione in una workstation o in un server.</span><span class="sxs-lookup"><span data-stu-id="9d5f6-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d5f6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9d5f6-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d5f6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9d5f6-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="9d5f6-106">Membri</span><span class="sxs-lookup"><span data-stu-id="9d5f6-106">Members</span></span>  
  
|<span data-ttu-id="9d5f6-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="9d5f6-107">Member name</span></span>|<span data-ttu-id="9d5f6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9d5f6-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="9d5f6-109">Il garbage collector è in esecuzione in una workstation.</span><span class="sxs-lookup"><span data-stu-id="9d5f6-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="9d5f6-110">Il garbage collector è in esecuzione in un server.</span><span class="sxs-lookup"><span data-stu-id="9d5f6-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d5f6-111">Note</span><span class="sxs-lookup"><span data-stu-id="9d5f6-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d5f6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9d5f6-112">Requirements</span></span>  
 <span data-ttu-id="9d5f6-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d5f6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d5f6-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9d5f6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9d5f6-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d5f6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d5f6-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d5f6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d5f6-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9d5f6-117">See also</span></span>

- [<span data-ttu-id="9d5f6-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="9d5f6-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
