---
title: Struttura COR_DEBUG_STEP_RANGE
ms.date: 03/30/2017
api_name:
- COR_DEBUG_STEP_RANGE
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_DEBUG_STEP_RANGE
helpviewer_keywords:
- COR_DEBUG_STEP_RANGE structure [.NET Framework debugging]
ms.assetid: 8809d00e-beaa-4dcf-b4e8-e89d0a5406b7
topic_type:
- apiref
ms.openlocfilehash: 206e4fb232f4786a76525d24aa379b25d6d2f71d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099352"
---
# <a name="cor_debug_step_range-structure"></a><span data-ttu-id="d83a6-102">Struttura COR_DEBUG_STEP_RANGE</span><span class="sxs-lookup"><span data-stu-id="d83a6-102">COR_DEBUG_STEP_RANGE Structure</span></span>
<span data-ttu-id="d83a6-103">Contene le informazioni sugli offset per un intervallo di codice.</span><span class="sxs-lookup"><span data-stu-id="d83a6-103">Contains the offset information for a range of code.</span></span>  
  
 <span data-ttu-id="d83a6-104">Questa struttura viene utilizzata dal metodo [ICorDebugStepper:: StepRange](icordebugstepper-steprange-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d83a6-104">This structure is used by the [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d83a6-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d83a6-105">Syntax</span></span>  
  
```cpp  
typedef struct {  
    ULONG32 startOffset;  
    ULONG32 endOffset;  
} COR_DEBUG_STEP_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="d83a6-106">Members</span><span class="sxs-lookup"><span data-stu-id="d83a6-106">Members</span></span>  
  
|<span data-ttu-id="d83a6-107">Member</span><span class="sxs-lookup"><span data-stu-id="d83a6-107">Member</span></span>|<span data-ttu-id="d83a6-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d83a6-108">Description</span></span>|  
|------------|-----------------|  
|`startOffset`|<span data-ttu-id="d83a6-109">Offset dell'inizio dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="d83a6-109">The offset of the beginning of the range.</span></span>|  
|`endOffset`|<span data-ttu-id="d83a6-110">Offset della fine dell'intervallo.</span><span class="sxs-lookup"><span data-stu-id="d83a6-110">The offset of the end of the range.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d83a6-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d83a6-111">Requirements</span></span>  
 <span data-ttu-id="d83a6-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d83a6-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d83a6-113">**Intestazione:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="d83a6-113">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d83a6-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d83a6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d83a6-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d83a6-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d83a6-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d83a6-116">See also</span></span>

- [<span data-ttu-id="d83a6-117">Metodo StepRange</span><span class="sxs-lookup"><span data-stu-id="d83a6-117">StepRange Method</span></span>](icordebugstepper-steprange-method.md)
- [<span data-ttu-id="d83a6-118">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="d83a6-118">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d83a6-119">Debug</span><span class="sxs-lookup"><span data-stu-id="d83a6-119">Debugging</span></span>](index.md)
