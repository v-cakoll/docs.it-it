---
title: Struttura CorDebugExceptionObjectStackFrame
ms.date: 03/30/2017
api_name:
- CorDebugExceptionObjectStackFrame
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugExceptionObjectStackFrame
helpviewer_keywords:
- CorDebugExceptionObjectStackFrame structure [.NET Framework debugging]
ms.assetid: 542cdd81-5ae7-4361-b0ef-1ae4775df258
topic_type:
- apiref
ms.openlocfilehash: 7eccaf984b187e463195bb3804f87bbb2c7ad47b
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795924"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="714d6-102">Struttura CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="714d6-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="714d6-103">Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.</span><span class="sxs-lookup"><span data-stu-id="714d6-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="714d6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="714d6-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="714d6-105">Members</span><span class="sxs-lookup"><span data-stu-id="714d6-105">Members</span></span>  
  
|<span data-ttu-id="714d6-106">Membro</span><span class="sxs-lookup"><span data-stu-id="714d6-106">Member</span></span>|<span data-ttu-id="714d6-107">Description</span><span class="sxs-lookup"><span data-stu-id="714d6-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="714d6-108">Puntatore all'oggetto ICorDebugModule per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="714d6-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="714d6-109">Valore del puntatore all'istruzione (PEI/RIP) per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="714d6-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="714d6-110">Token del metodo per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="714d6-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="714d6-111">Valore che indica se il frame è l'ultimo frame in un'eccezione esterna.</span><span class="sxs-lookup"><span data-stu-id="714d6-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="714d6-112">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="714d6-112">Remarks</span></span>  
 <span data-ttu-id="714d6-113">Il chiamante deve rilasciare il puntatore all'oggetto ICorDebugModule quando non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="714d6-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="714d6-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="714d6-114">Requirements</span></span>  
 <span data-ttu-id="714d6-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="714d6-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="714d6-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="714d6-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="714d6-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="714d6-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="714d6-118">**Versioni .NET Framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="714d6-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="714d6-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="714d6-119">See also</span></span>

- [<span data-ttu-id="714d6-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="714d6-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="714d6-121">Debug</span><span class="sxs-lookup"><span data-stu-id="714d6-121">Debugging</span></span>](index.md)
