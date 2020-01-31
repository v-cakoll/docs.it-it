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
ms.openlocfilehash: 2845c15d67e287d6efb0cd0a9c940b69de3a1c0c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789373"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="39c0b-102">Struttura CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="39c0b-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="39c0b-103">Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.</span><span class="sxs-lookup"><span data-stu-id="39c0b-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39c0b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="39c0b-104">Syntax</span></span>  
  
```cpp  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="39c0b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="39c0b-105">Members</span></span>  
  
|<span data-ttu-id="39c0b-106">Member</span><span class="sxs-lookup"><span data-stu-id="39c0b-106">Member</span></span>|<span data-ttu-id="39c0b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="39c0b-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="39c0b-108">Puntatore all'oggetto ICorDebugModule per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="39c0b-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="39c0b-109">Valore del puntatore all'istruzione (PEI/RIP) per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="39c0b-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="39c0b-110">Token del metodo per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="39c0b-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="39c0b-111">Valore che indica se il frame è l'ultimo frame in un'eccezione esterna.</span><span class="sxs-lookup"><span data-stu-id="39c0b-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39c0b-112">Note</span><span class="sxs-lookup"><span data-stu-id="39c0b-112">Remarks</span></span>  
 <span data-ttu-id="39c0b-113">Il chiamante deve rilasciare il puntatore all'oggetto ICorDebugModule quando non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="39c0b-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="39c0b-114">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="39c0b-114">Requirements</span></span>  
 <span data-ttu-id="39c0b-115">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="39c0b-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="39c0b-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="39c0b-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="39c0b-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="39c0b-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="39c0b-118">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="39c0b-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39c0b-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="39c0b-119">See also</span></span>

- [<span data-ttu-id="39c0b-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="39c0b-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="39c0b-121">Debug</span><span class="sxs-lookup"><span data-stu-id="39c0b-121">Debugging</span></span>](index.md)
