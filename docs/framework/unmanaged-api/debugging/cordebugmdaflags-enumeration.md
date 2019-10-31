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
ms.openlocfilehash: c7af194351290ad937e40a2fc8b960c2c242629c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132800"
---
# <a name="cordebugmdaflags-enumeration"></a><span data-ttu-id="7fc47-102">Enumerazione CorDebugMDAFlags</span><span class="sxs-lookup"><span data-stu-id="7fc47-102">CorDebugMDAFlags Enumeration</span></span>
<span data-ttu-id="7fc47-103">Specifica lo stato del thread su cui è attivato l'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="7fc47-103">Specifies the status of the thread on which the managed debugging assistant (MDA) is fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fc47-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fc47-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugMDAFlags {  
    MDA_FLAG_SLIP = 0x2  
} CorDebugMDAFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="7fc47-105">Members</span><span class="sxs-lookup"><span data-stu-id="7fc47-105">Members</span></span>  
  
|<span data-ttu-id="7fc47-106">Member</span><span class="sxs-lookup"><span data-stu-id="7fc47-106">Member</span></span>|<span data-ttu-id="7fc47-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fc47-107">Description</span></span>|  
|------------|-----------------|  
|`MDA_FLAG_SLIP`|<span data-ttu-id="7fc47-108">Il thread in cui è stato attivato l'assistente al debug gestito è stato slittato dopo l'attivazione dell'assistente al debug gestito.</span><span class="sxs-lookup"><span data-stu-id="7fc47-108">The thread on which the MDA was fired has slipped since the MDA was fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fc47-109">Note</span><span class="sxs-lookup"><span data-stu-id="7fc47-109">Remarks</span></span>  
 <span data-ttu-id="7fc47-110">Quando lo stack di chiamate non descrive più la posizione in cui è stato originariamente generato l'assistente al debug gestito, il thread viene considerato *slittato*.</span><span class="sxs-lookup"><span data-stu-id="7fc47-110">When the call stack no longer describes where the MDA was originally raised, the thread is considered to have *slipped*.</span></span> <span data-ttu-id="7fc47-111">Si tratta di una circostanza insolita dall'esecuzione di un'operazione non valida al momento dell'uscita del thread.</span><span class="sxs-lookup"><span data-stu-id="7fc47-111">This is an unusual circumstance brought about by the thread's execution of an invalid operation upon exiting.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fc47-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7fc47-112">Requirements</span></span>  
 <span data-ttu-id="7fc47-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fc47-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fc47-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7fc47-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7fc47-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7fc47-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7fc47-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fc47-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fc47-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fc47-117">See also</span></span>

- [<span data-ttu-id="7fc47-118">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="7fc47-118">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
