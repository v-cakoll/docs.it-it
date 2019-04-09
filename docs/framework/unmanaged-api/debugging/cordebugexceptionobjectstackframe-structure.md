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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a4cd4d353c22921ed3dba1dc08fe2cee7e429f8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59173082"
---
# <a name="cordebugexceptionobjectstackframe-structure"></a><span data-ttu-id="bdee9-102">Struttura CorDebugExceptionObjectStackFrame</span><span class="sxs-lookup"><span data-stu-id="bdee9-102">CorDebugExceptionObjectStackFrame Structure</span></span>
<span data-ttu-id="bdee9-103">Rappresenta le informazioni sullo stack frame da un oggetto di eccezione.</span><span class="sxs-lookup"><span data-stu-id="bdee9-103">Represents stack frame information from an exception object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdee9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bdee9-104">Syntax</span></span>  
  
```  
typedef struct CorDebugExceptionObjectStackFrame {  
    ICorDebugModule* pModule;  
    CORDB_ADDRESS ip;  
    mdMethodDef methodDef;  
    BOOL isLastForeignExceptionFrame;  
} CorDebugExceptionObjectStackFrame;  
```  
  
## <a name="members"></a><span data-ttu-id="bdee9-105">Membri</span><span class="sxs-lookup"><span data-stu-id="bdee9-105">Members</span></span>  
  
|<span data-ttu-id="bdee9-106">Member</span><span class="sxs-lookup"><span data-stu-id="bdee9-106">Member</span></span>|<span data-ttu-id="bdee9-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bdee9-107">Description</span></span>|  
|------------|-----------------|  
|`pModule`|<span data-ttu-id="bdee9-108">Un puntatore all'oggetto ICorDebugModule per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="bdee9-108">A pointer to the ICorDebugModule object for the current frame.</span></span>|  
|`ip`|<span data-ttu-id="bdee9-109">Il valore del puntatore all'istruzione (EIP/RIP) per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="bdee9-109">The value of the instruction pointer (EIP/RIP) for the current frame.</span></span>|  
|`methodDef`|<span data-ttu-id="bdee9-110">Il token del metodo per il frame corrente.</span><span class="sxs-lookup"><span data-stu-id="bdee9-110">The method token for the current frame.</span></span>|  
|`isLastForeignExceptionFrame`|<span data-ttu-id="bdee9-111">Un valore che indica se il frame è ultimo frame di un'eccezione esterna.</span><span class="sxs-lookup"><span data-stu-id="bdee9-111">A value that indicates whether the frame is the last frame in a foreign exception.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bdee9-112">Note</span><span class="sxs-lookup"><span data-stu-id="bdee9-112">Remarks</span></span>  
 <span data-ttu-id="bdee9-113">Il chiamante deve rilasciare il puntatore all'oggetto ICorDebugModule una volta non è più in uso.</span><span class="sxs-lookup"><span data-stu-id="bdee9-113">The caller must release the pointer to the ICorDebugModule object once it is no longer in use.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdee9-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bdee9-114">Requirements</span></span>  
 <span data-ttu-id="bdee9-115">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdee9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdee9-116">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bdee9-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bdee9-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bdee9-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="bdee9-118">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="bdee9-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="bdee9-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bdee9-119">See also</span></span>

- [<span data-ttu-id="bdee9-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="bdee9-120">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="bdee9-121">Debug</span><span class="sxs-lookup"><span data-stu-id="bdee9-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
