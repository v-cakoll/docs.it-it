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
ms.openlocfilehash: 29781666c106755f96f945325e3a8953bf93b211
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790352"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="2227b-102">Enumerazione LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="2227b-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="2227b-103">Indica l'operazione che è stata eseguita su un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="2227b-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2227b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2227b-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="2227b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="2227b-105">Members</span></span>  
  
|<span data-ttu-id="2227b-106">Member</span><span class="sxs-lookup"><span data-stu-id="2227b-106">Member</span></span>|<span data-ttu-id="2227b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2227b-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="2227b-108">È stata creata un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="2227b-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="2227b-109">Un'opzione di debug/traccia è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="2227b-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="2227b-110">Un'opzione di debug/traccia è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="2227b-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2227b-111">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="2227b-111">Requirements</span></span>  
 <span data-ttu-id="2227b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2227b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2227b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2227b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2227b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2227b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2227b-115">**Versioni .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2227b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2227b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2227b-116">See also</span></span>

- [<span data-ttu-id="2227b-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="2227b-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
