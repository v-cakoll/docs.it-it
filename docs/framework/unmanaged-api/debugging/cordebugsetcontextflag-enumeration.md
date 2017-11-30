---
title: Enumerazione CorDebugSetContextFlag
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugSetContextFlag
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugSetContextFlag
helpviewer_keywords: CorDebugSetContextFlag enumeration [.NET Framework debugging]
ms.assetid: b30280bb-fe75-44ed-8589-bcff081fae44
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 958ed303fab3dcb01fad2040dd06381e76fe5a00
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugsetcontextflag-enumeration"></a><span data-ttu-id="67497-102">Enumerazione CorDebugSetContextFlag</span><span class="sxs-lookup"><span data-stu-id="67497-102">CorDebugSetContextFlag Enumeration</span></span>
<span data-ttu-id="67497-103">Indica se il contesto proviene dal frame attivo (o foglia) sullo stack o se è stato calcolato dalla rimozione da un altro frame.</span><span class="sxs-lookup"><span data-stu-id="67497-103">Indicates whether the context is from the active (or leaf) frame on the stack or has been computed by unwinding from another frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67497-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67497-104">Syntax</span></span>  
  
```  
typedef enum CorDebugSetContextFlag  
{  
   SET_CONTEXT_FLAG_ACTIVE_FRAME = 1  
   SET_CONTEXT_FLAG_UNWIND_FRAME = 2  
}  CorDebugSetContextFlag;  
```  
  
## <a name="members"></a><span data-ttu-id="67497-105">Membri</span><span class="sxs-lookup"><span data-stu-id="67497-105">Members</span></span>  
  
|<span data-ttu-id="67497-106">Membro</span><span class="sxs-lookup"><span data-stu-id="67497-106">Member</span></span>|<span data-ttu-id="67497-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="67497-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="67497-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span><span class="sxs-lookup"><span data-stu-id="67497-108">SET_CONTEXT_FLAG_ACTIVE_FRAME</span></span>|<span data-ttu-id="67497-109">Il contesto è il contesto del thread attivo.</span><span class="sxs-lookup"><span data-stu-id="67497-109">The context is the thread’s active context.</span></span>|  
|<span data-ttu-id="67497-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span><span class="sxs-lookup"><span data-stu-id="67497-110">SET_CONTEXT_FLAG_UNWIND_FRAME</span></span>|<span data-ttu-id="67497-111">Il contesto è stato calcolato dalla rimozione da un altro frame.</span><span class="sxs-lookup"><span data-stu-id="67497-111">The context has been computed by unwinding from another frame.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67497-112">Note</span><span class="sxs-lookup"><span data-stu-id="67497-112">Remarks</span></span>  
 <span data-ttu-id="67497-113">`CorDebugSetContextFlag`Fornisce i valori utilizzati per il [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="67497-113">`CorDebugSetContextFlag` provides values that are used by the [ICorDebugStackWalk::SetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-setcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67497-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67497-114">Requirements</span></span>  
 <span data-ttu-id="67497-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67497-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67497-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="67497-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67497-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67497-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67497-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67497-118">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67497-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="67497-119">See Also</span></span>  
 [<span data-ttu-id="67497-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="67497-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="67497-121">Debug</span><span class="sxs-lookup"><span data-stu-id="67497-121">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
