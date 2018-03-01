---
title: Enumerazione CorDebugMDAFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorDebugMDAFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugMDAFlags
helpviewer_keywords:
- CorDebugMDAFlags enumeration [.NET Framework debugging]
ms.assetid: 7c0c92fe-8bd2-477f-b307-aca0143732ca
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: defd2572d6f925cf557539983308b3b3e900eebd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="ac959-102">Enumerazione CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="ac959-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="ac959-103">Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ac959-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac959-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac959-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ac959-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ac959-105">Members</span></span>  
  
|<span data-ttu-id="ac959-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ac959-106">Member</span></span>|<span data-ttu-id="ac959-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac959-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="ac959-108">Il thread su cui è stato attivato l'assistente al debug gestito è stato ignorato poiché è stato attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="ac959-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac959-109">Note</span><span class="sxs-lookup"><span data-stu-id="ac959-109">Remarks</span></span>  
 <span data-ttu-id="ac959-110">Quando lo stack di chiamate non descrive in cui è stato originariamente generato l'assistente al debug gestito, il thread è considerato *ignorato*.</span><span class="sxs-lookup"><span data-stu-id="ac959-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="ac959-111">Si tratta di una situazione insolita causata dall'esecuzione del thread dell'operazione non valida all'uscita.</span><span class="sxs-lookup"><span data-stu-id="ac959-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac959-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac959-112">Requirements</span></span>  
 <span data-ttu-id="ac959-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac959-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac959-114">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ac959-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac959-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac959-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac959-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac959-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac959-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac959-117">See Also</span></span>  
 [<span data-ttu-id="ac959-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ac959-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
