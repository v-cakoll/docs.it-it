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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c1707a09f14fbab6150c2ecbcd188d7bf88064fa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61989664"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="d6e52-102">Enumerazione CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="d6e52-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="d6e52-103">Specifica la generazione di un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="d6e52-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6e52-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6e52-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="d6e52-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d6e52-105">Members</span></span>  
  
|<span data-ttu-id="d6e52-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="d6e52-106">Member name</span></span>|<span data-ttu-id="d6e52-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6e52-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="d6e52-108">Generazione 0.</span><span class="sxs-lookup"><span data-stu-id="d6e52-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="d6e52-109">Generazione 1.</span><span class="sxs-lookup"><span data-stu-id="d6e52-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="d6e52-110">Generazione 2.</span><span class="sxs-lookup"><span data-stu-id="d6e52-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="d6e52-111">L'heap oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="d6e52-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6e52-112">Note</span><span class="sxs-lookup"><span data-stu-id="d6e52-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6e52-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6e52-113">Requirements</span></span>  
 <span data-ttu-id="d6e52-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6e52-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6e52-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d6e52-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d6e52-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d6e52-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d6e52-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6e52-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e52-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6e52-118">See also</span></span>

- [<span data-ttu-id="d6e52-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="d6e52-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
