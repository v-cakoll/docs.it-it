---
title: Enumerazione CorDebugExceptionFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugExceptionFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugExceptionFlags
helpviewer_keywords: CorDebugExceptionFlags enumeration [.NET Framework debugging]
ms.assetid: b22687a8-e9cf-4e65-a1b0-f92a81bc524e
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1b25211c8e7f03cc09e8729abc44af39f0c84259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugexceptionflags-enumeration"></a><span data-ttu-id="4b571-102">Enumerazione CorDebugExceptionFlags</span><span class="sxs-lookup"><span data-stu-id="4b571-102">CorDebugExceptionFlags Enumeration</span></span>
<span data-ttu-id="4b571-103">Offre informazioni aggiuntive su un'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4b571-103">Provides additional information about an exception.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b571-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4b571-104">Syntax</span></span>  
  
```  
typedef enum CorDebugExceptionFlags {  
    DEBUG_EXCEPTION_NONE = 0,  
    DEBUG_EXCEPTION_CAN_BE_INTERCEPTED = 0x0001  
} CorDebugExceptionFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="4b571-105">Membri</span><span class="sxs-lookup"><span data-stu-id="4b571-105">Members</span></span>  
  
|<span data-ttu-id="4b571-106">Membro</span><span class="sxs-lookup"><span data-stu-id="4b571-106">Member</span></span>|<span data-ttu-id="4b571-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4b571-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_EXCEPTION_NONE`|<span data-ttu-id="4b571-108">Nessuna eccezione.</span><span class="sxs-lookup"><span data-stu-id="4b571-108">There is no exception.</span></span>|  
|`DEBUG_EXCEPTION_CAN_BE_INTERCEPTED`|<span data-ttu-id="4b571-109">L'eccezione è intercettabile.</span><span class="sxs-lookup"><span data-stu-id="4b571-109">The exception is interceptable.</span></span><br /><br /> <span data-ttu-id="4b571-110">È possibile che la temporizzazione dell'eccezione non consenta al debugger di intercettarla.</span><span class="sxs-lookup"><span data-stu-id="4b571-110">The timing of the exception may still be such that the debugger cannot intercept it.</span></span> <span data-ttu-id="4b571-111">Ad esempio, in assenza di codice gestito sotto il callback corrente o se l'evento di eccezione è stato generato da un allegato JIT, non è possibile intercettare l'eccezione.</span><span class="sxs-lookup"><span data-stu-id="4b571-111">For example, if there is no managed code below the current callback or the exception event resulted from a just-in-time (JIT) attachment, the exception cannot be intercepted.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b571-112">Note</span><span class="sxs-lookup"><span data-stu-id="4b571-112">Remarks</span></span>  
 <span data-ttu-id="4b571-113">È possibile che nelle versioni successive vengano aggiunti nuovi valori a questa enumerazione, quindi è necessario predisporre codice che usa `CorDebugExceptionFlags` per i valori non previsti.</span><span class="sxs-lookup"><span data-stu-id="4b571-113">New values may be added to this enumeration in later versions, so you should prepare code that uses `CorDebugExceptionFlags` for unexpected values.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b571-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4b571-114">Requirements</span></span>  
 <span data-ttu-id="4b571-115">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b571-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b571-116">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="4b571-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4b571-117">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b571-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b571-118">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b571-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b571-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b571-119">See Also</span></span>  
 [<span data-ttu-id="4b571-120">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="4b571-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
