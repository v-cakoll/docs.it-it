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
ms.openlocfilehash: 193f5ffe96e89a00bed8a3c88ee346ba3ea9f2b4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740022"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="9dec9-102">Enumerazione CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="9dec9-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="9dec9-103">Specifica la generazione di un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="9dec9-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dec9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9dec9-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="9dec9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9dec9-105">Members</span></span>  
  
|<span data-ttu-id="9dec9-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="9dec9-106">Member name</span></span>|<span data-ttu-id="9dec9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9dec9-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="9dec9-108">Generazione 0.</span><span class="sxs-lookup"><span data-stu-id="9dec9-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="9dec9-109">Generazione 1.</span><span class="sxs-lookup"><span data-stu-id="9dec9-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="9dec9-110">Generazione 2.</span><span class="sxs-lookup"><span data-stu-id="9dec9-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="9dec9-111">L'heap oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="9dec9-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9dec9-112">Note</span><span class="sxs-lookup"><span data-stu-id="9dec9-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dec9-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9dec9-113">Requirements</span></span>  
 <span data-ttu-id="9dec9-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dec9-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dec9-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9dec9-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9dec9-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dec9-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dec9-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dec9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dec9-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9dec9-118">See also</span></span>

- [<span data-ttu-id="9dec9-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="9dec9-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
