---
title: Enumerazione LogSwitchCallReason
ms.date: 03/30/2017
api_name:
- LogSwitchCallReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- LogSwitchCallReason
helpviewer_keywords:
- LogSwitchCallReason enumeration [.NET Framework debugging]
ms.assetid: 5bbb8d1b-bbc4-47b0-b1b1-2d54cc0be291
topic_type:
- apiref
ms.openlocfilehash: 2a6ca9f4d74c508ac0a2af68c2a5b0a3e6d6b217
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139178"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="0173e-102">Enumerazione LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="0173e-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="0173e-103">Indica l'operazione che è stata eseguita su un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="0173e-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0173e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0173e-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="0173e-105">Members</span><span class="sxs-lookup"><span data-stu-id="0173e-105">Members</span></span>  
  
|<span data-ttu-id="0173e-106">Member</span><span class="sxs-lookup"><span data-stu-id="0173e-106">Member</span></span>|<span data-ttu-id="0173e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0173e-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="0173e-108">È stata creata un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="0173e-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="0173e-109">Un'opzione di debug/traccia è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="0173e-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="0173e-110">Un'opzione di debug/traccia è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="0173e-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0173e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0173e-111">Requirements</span></span>  
 <span data-ttu-id="0173e-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0173e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0173e-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0173e-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0173e-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0173e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0173e-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0173e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0173e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0173e-116">See also</span></span>

- [<span data-ttu-id="0173e-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="0173e-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
