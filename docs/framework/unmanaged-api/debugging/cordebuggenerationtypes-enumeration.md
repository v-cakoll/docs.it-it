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
ms.openlocfilehash: 362e917e1684c91bde80a8b5c2e6a27a18a99190
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098204"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="25ba5-102">Enumerazione CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="25ba5-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="25ba5-103">Specifica la generazione di un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="25ba5-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25ba5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="25ba5-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="25ba5-105">Members</span><span class="sxs-lookup"><span data-stu-id="25ba5-105">Members</span></span>  
  
|<span data-ttu-id="25ba5-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="25ba5-106">Member name</span></span>|<span data-ttu-id="25ba5-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25ba5-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="25ba5-108">Generazione 0.</span><span class="sxs-lookup"><span data-stu-id="25ba5-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="25ba5-109">Generazione 1.</span><span class="sxs-lookup"><span data-stu-id="25ba5-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="25ba5-110">Generazione 2.</span><span class="sxs-lookup"><span data-stu-id="25ba5-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="25ba5-111">Heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="25ba5-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="25ba5-112">Note</span><span class="sxs-lookup"><span data-stu-id="25ba5-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="25ba5-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="25ba5-113">Requirements</span></span>  
 <span data-ttu-id="25ba5-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="25ba5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="25ba5-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="25ba5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="25ba5-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="25ba5-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="25ba5-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="25ba5-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25ba5-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="25ba5-118">See also</span></span>

- [<span data-ttu-id="25ba5-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="25ba5-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
