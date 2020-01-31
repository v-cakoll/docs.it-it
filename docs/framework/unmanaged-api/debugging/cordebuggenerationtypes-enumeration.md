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
ms.openlocfilehash: 6133b34a60fd06c1b75d69783760741b8de62071
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789352"
---
# <a name="cordebuggenerationtypes-enumeration"></a><span data-ttu-id="f1f9a-102">Enumerazione CorDebugGenerationTypes</span><span class="sxs-lookup"><span data-stu-id="f1f9a-102">CorDebugGenerationTypes Enumeration</span></span>
<span data-ttu-id="f1f9a-103">Specifica la generazione di un'area di memoria nell'heap gestito.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-103">Specifies the generation of a region of memory on the managed heap.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1f9a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f1f9a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugGenerationTypes {  
    CorDebug_Gen0 = 0,  
    CorDebug_Gen1 = 1,  
    CorDebug_Gen2 = 2,  
    CorDebug_LOH  = 3,  
} CorDebugRegionTypes;  
```  
  
## <a name="members"></a><span data-ttu-id="f1f9a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f1f9a-105">Members</span></span>  
  
|<span data-ttu-id="f1f9a-106">Nome membro</span><span class="sxs-lookup"><span data-stu-id="f1f9a-106">Member name</span></span>|<span data-ttu-id="f1f9a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f1f9a-107">Description</span></span>|  
|-----------------|-----------------|  
|`CorDebug_Gen0`|<span data-ttu-id="f1f9a-108">Generazione 0.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-108">Generation 0.</span></span>|  
|`CorDebug_Gen1`|<span data-ttu-id="f1f9a-109">Generazione 1.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-109">Generation 1.</span></span>|  
|`CorDebug_Gen2`|<span data-ttu-id="f1f9a-110">Generazione 2.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-110">Generation 2.</span></span>|  
|`CorDebug_LOH`|<span data-ttu-id="f1f9a-111">Heap degli oggetti grandi.</span><span class="sxs-lookup"><span data-stu-id="f1f9a-111">The large object heap.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f1f9a-112">Note</span><span class="sxs-lookup"><span data-stu-id="f1f9a-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1f9a-113">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="f1f9a-113">Requirements</span></span>  
 <span data-ttu-id="f1f9a-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1f9a-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1f9a-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f1f9a-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f1f9a-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1f9a-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1f9a-117">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1f9a-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1f9a-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f1f9a-118">See also</span></span>

- [<span data-ttu-id="f1f9a-119">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="f1f9a-119">Debugging Enumerations</span></span>](debugging-enumerations.md)
