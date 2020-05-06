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
ms.openlocfilehash: e024500ea66dcb42e712e07e976a709401160a27
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795768"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="23dfa-102">Enumerazione CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="23dfa-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="23dfa-103">Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="23dfa-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23dfa-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="23dfa-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="23dfa-105">Members</span><span class="sxs-lookup"><span data-stu-id="23dfa-105">Members</span></span>  
  
|<span data-ttu-id="23dfa-106">Membro</span><span class="sxs-lookup"><span data-stu-id="23dfa-106">Member</span></span>|<span data-ttu-id="23dfa-107">Description</span><span class="sxs-lookup"><span data-stu-id="23dfa-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="23dfa-108">Il thread in cui è stato attivato l'assistente al debug gestito è stato slittato dopo l'attivazione dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="23dfa-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23dfa-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="23dfa-109">Remarks</span></span>  
 <span data-ttu-id="23dfa-110">Quando lo stack di chiamate non descrive più la posizione in cui è stato originariamente generato l'assistente al debug gestito, il thread viene considerato *slittato*.</span><span class="sxs-lookup"><span data-stu-id="23dfa-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="23dfa-111">Si tratta di una circostanza insolita dall'esecuzione di un'operazione non valida al momento dell'uscita del thread.</span><span class="sxs-lookup"><span data-stu-id="23dfa-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23dfa-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23dfa-112">Requirements</span></span>  
 <span data-ttu-id="23dfa-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23dfa-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23dfa-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="23dfa-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="23dfa-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="23dfa-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="23dfa-116">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23dfa-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23dfa-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23dfa-117">See also</span></span>

- [<span data-ttu-id="23dfa-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="23dfa-118">Debugging Enumerations</span></span>](debugging-enumerations.md)
