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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182923"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="b4300-102">Enumerazione CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="b4300-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="b4300-103">Indica se un Garbage Collector è in esecuzione in una workstation o in un server.</span><span class="sxs-lookup"><span data-stu-id="b4300-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4300-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4300-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4300-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4300-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="b4300-106">Membri</span><span class="sxs-lookup"><span data-stu-id="b4300-106">Members</span></span>  
  
|<span data-ttu-id="b4300-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="b4300-107">Member name</span></span>|<span data-ttu-id="b4300-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b4300-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="b4300-109">Il garbage collector è in esecuzione in una workstation.</span><span class="sxs-lookup"><span data-stu-id="b4300-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="b4300-110">Il garbage collector è in esecuzione in un server.</span><span class="sxs-lookup"><span data-stu-id="b4300-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b4300-111">Note</span><span class="sxs-lookup"><span data-stu-id="b4300-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4300-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4300-112">Requirements</span></span>  
 <span data-ttu-id="b4300-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4300-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4300-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4300-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4300-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4300-115">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="b4300-116">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="b4300-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b4300-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b4300-117">See also</span></span>

- [<span data-ttu-id="b4300-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="b4300-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
