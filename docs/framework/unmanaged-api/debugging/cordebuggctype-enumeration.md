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
ms.openlocfilehash: 6f4c96517375df4cd249b72953bf37812a498c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789354"
---
# <a name="cordebuggctype-enumeration"></a><span data-ttu-id="7c9d8-102">Enumerazione CorDebugGCType</span><span class="sxs-lookup"><span data-stu-id="7c9d8-102">CorDebugGCType Enumeration</span></span>
<span data-ttu-id="7c9d8-103">Indica se un Garbage Collector è in esecuzione in una workstation o in un server.</span><span class="sxs-lookup"><span data-stu-id="7c9d8-103">Indicates whether the garbage collector is running on a workstation or a server.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7c9d8-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7c9d8-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGCType {  
    CorDebugWorkstationGC  = 0,  
    CorDebugServerGC       = ( CorDebugWorkstationGC + 1 )  
} CorDebugGCType;  
```  
  
## <a name="parameters"></a><span data-ttu-id="7c9d8-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7c9d8-105">Parameters</span></span>  
  
## <a name="members"></a><span data-ttu-id="7c9d8-106">Membri</span><span class="sxs-lookup"><span data-stu-id="7c9d8-106">Members</span></span>  
  
|<span data-ttu-id="7c9d8-107">Nome membro</span><span class="sxs-lookup"><span data-stu-id="7c9d8-107">Member name</span></span>|<span data-ttu-id="7c9d8-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7c9d8-108">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebugWorkstationGC`|<span data-ttu-id="7c9d8-109">Il Garbage Collector è in esecuzione su una workstation.</span><span class="sxs-lookup"><span data-stu-id="7c9d8-109">The garbage collector is running on a workstation.</span></span>|  
|`CorDebugServerGC`|<span data-ttu-id="7c9d8-110">Il Garbage Collector è in esecuzione in un server.</span><span class="sxs-lookup"><span data-stu-id="7c9d8-110">The garbage collector is running on a server.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7c9d8-111">Note</span><span class="sxs-lookup"><span data-stu-id="7c9d8-111">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7c9d8-112">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="7c9d8-112">Requirements</span></span>  
 <span data-ttu-id="7c9d8-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7c9d8-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7c9d8-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7c9d8-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7c9d8-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7c9d8-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7c9d8-116">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7c9d8-116">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7c9d8-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c9d8-117">See also</span></span>

- [<span data-ttu-id="7c9d8-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="7c9d8-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
