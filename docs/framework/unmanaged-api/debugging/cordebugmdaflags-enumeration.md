---
title: Enumerazione CorDebugMDAFlags
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 732523935eec62bffbc15705bc93c97f14c90064
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792717"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="6cd3b-102">Enumerazione CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="6cd3b-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="6cd3b-103">Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="6cd3b-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6cd3b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6cd3b-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="6cd3b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="6cd3b-105">Members</span></span>  
  
|<span data-ttu-id="6cd3b-106">Member</span><span class="sxs-lookup"><span data-stu-id="6cd3b-106">Member</span></span>|<span data-ttu-id="6cd3b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6cd3b-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="6cd3b-108">Il thread in cui è stato attivato l'assistente al debug gestito è stato ignorato poiché è stato attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="6cd3b-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6cd3b-109">Note</span><span class="sxs-lookup"><span data-stu-id="6cd3b-109">Remarks</span></span>  
 <span data-ttu-id="6cd3b-110">Quando lo stack di chiamate non descrive in cui è stato originariamente generato l'assistente al debug gestito, il thread è considerato *slittato*.</span><span class="sxs-lookup"><span data-stu-id="6cd3b-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="6cd3b-111">Si tratta di una situazione insolita causata dall'esecuzione del thread di un'operazione non valida all'uscita dal.</span><span class="sxs-lookup"><span data-stu-id="6cd3b-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6cd3b-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6cd3b-112">Requirements</span></span>  
 <span data-ttu-id="6cd3b-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6cd3b-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6cd3b-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6cd3b-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6cd3b-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6cd3b-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6cd3b-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6cd3b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cd3b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6cd3b-117">See also</span></span>

- [<span data-ttu-id="6cd3b-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="6cd3b-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
