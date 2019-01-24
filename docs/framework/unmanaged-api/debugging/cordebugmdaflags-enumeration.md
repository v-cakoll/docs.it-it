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
ms.openlocfilehash: b7f20dec86a85be85472037f58a2bd2002d9be1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620393"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="f60af-102">Enumerazione CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="f60af-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="f60af-103">Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f60af-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60af-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f60af-104">Syntax</span></span>  
  
```  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f60af-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f60af-105">Members</span></span>  
  
|<span data-ttu-id="f60af-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f60af-106">Member</span></span>|<span data-ttu-id="f60af-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f60af-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="f60af-108">Il thread in cui è stato attivato l'assistente al debug gestito è stato ignorato poiché è stato attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="f60af-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f60af-109">Note</span><span class="sxs-lookup"><span data-stu-id="f60af-109">Remarks</span></span>  
 <span data-ttu-id="f60af-110">Quando lo stack di chiamate non descrive in cui è stato originariamente generato l'assistente al debug gestito, il thread è considerato *slittato*.</span><span class="sxs-lookup"><span data-stu-id="f60af-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="f60af-111">Si tratta di una situazione insolita causata dall'esecuzione del thread di un'operazione non valida all'uscita dal.</span><span class="sxs-lookup"><span data-stu-id="f60af-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f60af-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f60af-112">Requirements</span></span>  
 <span data-ttu-id="f60af-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f60af-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60af-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f60af-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f60af-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f60af-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f60af-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60af-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f60af-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f60af-117">See also</span></span>
- [<span data-ttu-id="f60af-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="f60af-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
