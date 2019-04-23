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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59085896"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="c7d3a-102">Enumerazione CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="c7d3a-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="c7d3a-103">Specifica la generazione di un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7d3a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c7d3a-104">Syntax</span></span>  
  
```  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="c7d3a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c7d3a-105">Members</span></span>  
  
|<span data-ttu-id="c7d3a-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="c7d3a-106">Member name</span></span>|<span data-ttu-id="c7d3a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c7d3a-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="c7d3a-108">Generazione 0.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="c7d3a-109">Generazione 1.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="c7d3a-110">Generazione 2.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="c7d3a-111">L'heap oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="c7d3a-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c7d3a-112">Note</span><span class="sxs-lookup"><span data-stu-id="c7d3a-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7d3a-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c7d3a-113">Requirements</span></span>  
 <span data-ttu-id="c7d3a-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7d3a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7d3a-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c7d3a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c7d3a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7d3a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7d3a-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7d3a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7d3a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c7d3a-118">See also</span></span>

- [<span data-ttu-id="c7d3a-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="c7d3a-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
