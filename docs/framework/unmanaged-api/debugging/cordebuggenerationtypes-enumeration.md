---
title: Enumerazione CorDebugGenerationTypes
ms.date: 03/30/2017
api_name:
- CorDebugGenerationTypes
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGenerationTypes
helpviewer_keywords:
- CorDebugGenerationTypes enumeration [.NET Framework debugging]
ms.assetid: 9f25b64f-eedd-4ae5-8b0e-cfdfb9b6c5d8
topic_type:
- apiref
ms.openlocfilehash: 0443f58b79e60111756308cc4843daf86d1fc823
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795865"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="84e4d-102">Enumerazione CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="84e4d-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="84e4d-103">Specifica la generazione di un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="84e4d-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84e4d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84e4d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="84e4d-105">Members</span><span class="sxs-lookup"><span data-stu-id="84e4d-105">Members</span></span>  
  
|<span data-ttu-id="84e4d-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="84e4d-106">Member name</span></span>|<span data-ttu-id="84e4d-107">Description</span><span class="sxs-lookup"><span data-stu-id="84e4d-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="84e4d-108">Generazione 0.</span><span class="sxs-lookup"><span data-stu-id="84e4d-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="84e4d-109">Prima generazione.</span><span class="sxs-lookup"><span data-stu-id="84e4d-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="84e4d-110">Generazione 2.</span><span class="sxs-lookup"><span data-stu-id="84e4d-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="84e4d-111">Heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="84e4d-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84e4d-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="84e4d-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84e4d-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="84e4d-113">Requirements</span></span>  
 <span data-ttu-id="84e4d-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84e4d-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84e4d-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="84e4d-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="84e4d-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="84e4d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="84e4d-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84e4d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e4d-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84e4d-118">See also</span></span>

- [<span data-ttu-id="84e4d-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="84e4d-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
