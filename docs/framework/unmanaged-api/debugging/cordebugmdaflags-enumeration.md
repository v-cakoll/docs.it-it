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
ms.openlocfilehash: bf9f7f3d3419efc9e1dc7d75fc7272432c0cf5d0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739698"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="64a7a-102">Enumerazione CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="64a7a-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="64a7a-103">Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="64a7a-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64a7a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="64a7a-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="64a7a-105">Membri</span><span class="sxs-lookup"><span data-stu-id="64a7a-105">Members</span></span>  
  
|<span data-ttu-id="64a7a-106">Member</span><span class="sxs-lookup"><span data-stu-id="64a7a-106">Member</span></span>|<span data-ttu-id="64a7a-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="64a7a-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="64a7a-108">Il thread in cui è stato attivato l'assistente al debug gestito è stato ignorato poiché è stato attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="64a7a-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="64a7a-109">Note</span><span class="sxs-lookup"><span data-stu-id="64a7a-109">Remarks</span></span>  
 <span data-ttu-id="64a7a-110">Quando lo stack di chiamate non descrive in cui è stato originariamente generato l'assistente al debug gestito, il thread è considerato *slittato*.</span><span class="sxs-lookup"><span data-stu-id="64a7a-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="64a7a-111">Si tratta di una situazione insolita causata dall'esecuzione del thread di un'operazione non valida all'uscita dal.</span><span class="sxs-lookup"><span data-stu-id="64a7a-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64a7a-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="64a7a-112">Requirements</span></span>  
 <span data-ttu-id="64a7a-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64a7a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64a7a-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64a7a-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64a7a-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64a7a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64a7a-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64a7a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64a7a-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="64a7a-117">See also</span></span>

- [<span data-ttu-id="64a7a-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="64a7a-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
