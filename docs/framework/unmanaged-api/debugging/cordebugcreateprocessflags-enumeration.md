---
title: Enumerazione CorDebugCreateProcessFlags
ms.date: 03/30/2017
api_name:
- CorDebugCreateProcessFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugCreateProcessFlags
helpviewer_keywords:
- CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type:
- apiref
ms.openlocfilehash: c0e4c43ac18b5e214d38dd7a57452a3871e4b43d
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/05/2020
ms.locfileid: "82796028"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="f424d-102">Enumerazione CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="f424d-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="f424d-103">Fornisce opzioni di debug aggiuntive che possono essere usate in una chiamata al metodo [ICorDebug:: CreateProcess](icordebug-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f424d-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f424d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f424d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="f424d-105">Members</span><span class="sxs-lookup"><span data-stu-id="f424d-105">Members</span></span>  
  
|<span data-ttu-id="f424d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f424d-106">Member</span></span>|<span data-ttu-id="f424d-107">Description</span><span class="sxs-lookup"><span data-stu-id="f424d-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="f424d-108">Non è stata impostata alcuna opzione speciale.</span><span class="sxs-lookup"><span data-stu-id="f424d-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f424d-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f424d-109">Requirements</span></span>  
 <span data-ttu-id="f424d-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f424d-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f424d-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f424d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f424d-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f424d-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f424d-113">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f424d-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f424d-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f424d-114">See also</span></span>

- [<span data-ttu-id="f424d-115">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="f424d-115">Debugging Enumerations</span></span>](debugging-enumerations.md)
