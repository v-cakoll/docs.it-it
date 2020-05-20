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
ms.openlocfilehash: 4d29bb3886ffb51e1dfb9654f4d70ef7c568fd43
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420708"
---
# <a name="logswitchcallreason-enumeration"></a><span data-ttu-id="1a08b-102">Enumerazione LogSwitchCallReason</span><span class="sxs-lookup"><span data-stu-id="1a08b-102">LogSwitchCallReason Enumeration</span></span>
<span data-ttu-id="1a08b-103">Indica l'operazione che è stata eseguita su un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="1a08b-103">Indicates the operation that was performed on a debugging/tracing switch.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1a08b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1a08b-104">Syntax</span></span>  
  
```cpp  
typedef enum LogSwitchCallReason {  
    SWITCH_CREATE,  
    SWITCH_MODIFY,  
    SWITCH_DELETE  
} LogSwitchCallReason;  
```  
  
## <a name="members"></a><span data-ttu-id="1a08b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="1a08b-105">Members</span></span>  
  
|<span data-ttu-id="1a08b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="1a08b-106">Member</span></span>|<span data-ttu-id="1a08b-107">Description</span><span class="sxs-lookup"><span data-stu-id="1a08b-107">Description</span></span>|  
|------------|-----------------|  
|`SWITCH_CREATE`|<span data-ttu-id="1a08b-108">È stata creata un'opzione di debug/traccia.</span><span class="sxs-lookup"><span data-stu-id="1a08b-108">A debugging/tracing switch was created.</span></span>|  
|`SWITCH_MODIFY`|<span data-ttu-id="1a08b-109">Un'opzione di debug/traccia è stata modificata.</span><span class="sxs-lookup"><span data-stu-id="1a08b-109">A debugging/tracing switch was modified.</span></span>|  
|`SWITCH_DELETE`|<span data-ttu-id="1a08b-110">Un'opzione di debug/traccia è stata eliminata.</span><span class="sxs-lookup"><span data-stu-id="1a08b-110">A debugging/tracing switch was deleted.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1a08b-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1a08b-111">Requirements</span></span>  
 <span data-ttu-id="1a08b-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1a08b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1a08b-113">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1a08b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1a08b-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1a08b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1a08b-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1a08b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1a08b-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1a08b-116">See also</span></span>

- [<span data-ttu-id="1a08b-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="1a08b-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
