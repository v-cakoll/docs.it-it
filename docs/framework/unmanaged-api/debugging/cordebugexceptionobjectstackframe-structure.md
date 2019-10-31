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
ms.openlocfilehash: faa2082d31c5fa47b87e2238017066b477fdc191
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132180"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="61b7e-102">Struttura CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="61b7e-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="61b7e-103">Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.</span><span class="sxs-lookup"><span data-stu-id="61b7e-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61b7e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="61b7e-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="61b7e-105">Members</span><span class="sxs-lookup"><span data-stu-id="61b7e-105">Members</span></span>  
  
|<span data-ttu-id="61b7e-106">Member</span><span class="sxs-lookup"><span data-stu-id="61b7e-106">Member</span></span>|<span data-ttu-id="61b7e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="61b7e-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="61b7e-108">Puntatore all'oggetto ICorDebugModule per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="61b7e-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="61b7e-109">Valore del puntatore all'istruzione (PEI/RIP) per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="61b7e-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="61b7e-110">Token del metodo per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="61b7e-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="61b7e-111">Valore che indica se il frame è l'ultimo frame in un'eccezione esterna.</span><span class="sxs-lookup"><span data-stu-id="61b7e-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61b7e-112">Note</span><span class="sxs-lookup"><span data-stu-id="61b7e-112">Remarks</span></span>  
 <span data-ttu-id="61b7e-113">Il chiamante deve rilasciare il puntatore all'oggetto ICorDebugModule quando non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="61b7e-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61b7e-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="61b7e-114">Requirements</span></span>  
 <span data-ttu-id="61b7e-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61b7e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61b7e-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="61b7e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="61b7e-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61b7e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61b7e-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61b7e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61b7e-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="61b7e-119">See also</span></span>

- [<span data-ttu-id="61b7e-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="61b7e-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="61b7e-121">Debug</span><span class="sxs-lookup"><span data-stu-id="61b7e-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
