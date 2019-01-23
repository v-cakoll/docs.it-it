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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bba39446d9ca5164d98337e93e83725cfa503903
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54515326"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="92954-102">Enumerazione LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="92954-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="92954-103">Indica l'operazione che è stata eseguita su un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="92954-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92954-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="92954-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="92954-105">Membri</span><span class="sxs-lookup"><span data-stu-id="92954-105">Members</span></span>  
  
|<span data-ttu-id="92954-106">Membro</span><span class="sxs-lookup"><span data-stu-id="92954-106">Member</span></span>|<span data-ttu-id="92954-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="92954-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="92954-108">È stato creato un commutatore di analisi o debug.</span><span class="sxs-lookup"><span data-stu-id="92954-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="92954-109">È stata modificata un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="92954-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="92954-110">Un'opzione di debug/traccia è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="92954-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="92954-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="92954-111">Requirements</span></span>  
 <span data-ttu-id="92954-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92954-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92954-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="92954-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="92954-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92954-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92954-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92954-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92954-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92954-116">See also</span></span>
- [<span data-ttu-id="92954-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="92954-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
