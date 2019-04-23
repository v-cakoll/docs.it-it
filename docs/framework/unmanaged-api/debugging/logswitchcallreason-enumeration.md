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
ms.openlocfilehash: 7eadb595eb62b4f1a9dcc888225cbb7454119c7c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59198491"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="787b7-102">Enumerazione LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="787b7-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="787b7-103">Indica l'operazione che è stata eseguita su un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="787b7-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787b7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="787b7-104">Syntax</span></span>  
  
```  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="787b7-105">Membri</span><span class="sxs-lookup"><span data-stu-id="787b7-105">Members</span></span>  
  
|<span data-ttu-id="787b7-106">Member</span><span class="sxs-lookup"><span data-stu-id="787b7-106">Member</span></span>|<span data-ttu-id="787b7-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="787b7-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="787b7-108">È stato creato un commutatore di analisi o debug.</span><span class="sxs-lookup"><span data-stu-id="787b7-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="787b7-109">È stata modificata un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="787b7-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="787b7-110">Un'opzione di debug/traccia è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="787b7-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="787b7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="787b7-111">Requirements</span></span>  
 <span data-ttu-id="787b7-112">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="787b7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="787b7-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="787b7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="787b7-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="787b7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="787b7-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="787b7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787b7-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="787b7-116">See also</span></span>

- [<span data-ttu-id="787b7-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="787b7-117">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
