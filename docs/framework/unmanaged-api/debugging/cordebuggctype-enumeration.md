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
ms.openlocfilehash: 8dd070d2c895a94ac996be81e672bd67f59b83b7
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795898"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="35db7-102">Enumerazione CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="35db7-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="35db7-103">Indica se un Garbage Collector è in esecuzione in una workstation o in un server.</span><span class="sxs-lookup"><span data-stu-id="35db7-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35db7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="35db7-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="35db7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="35db7-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="35db7-106">Members</span><span class="sxs-lookup"><span data-stu-id="35db7-106">Members</span></span>  
  
|<span data-ttu-id="35db7-107">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="35db7-107">Member name</span></span>|<span data-ttu-id="35db7-108">Description</span><span class="sxs-lookup"><span data-stu-id="35db7-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="35db7-109">Il Garbage Collector è in esecuzione su una workstation.</span><span class="sxs-lookup"><span data-stu-id="35db7-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="35db7-110">Il Garbage Collector è in esecuzione in un server.</span><span class="sxs-lookup"><span data-stu-id="35db7-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35db7-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="35db7-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35db7-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="35db7-112">Requirements</span></span>  
 <span data-ttu-id="35db7-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35db7-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35db7-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="35db7-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="35db7-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="35db7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="35db7-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35db7-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35db7-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="35db7-117">See also</span></span>

- [<span data-ttu-id="35db7-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="35db7-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
