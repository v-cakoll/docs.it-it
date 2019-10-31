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
ms.openlocfilehash: d28f6eab5390194a4089cbbaf1f586c3f53a7db5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132247"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="d85b6-102">Enumerazione CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="d85b6-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="d85b6-103">Fornisce opzioni di debug aggiuntive che possono essere usate in una chiamata al metodo [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d85b6-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d85b6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d85b6-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="d85b6-105">Members</span><span class="sxs-lookup"><span data-stu-id="d85b6-105">Members</span></span>  
  
|<span data-ttu-id="d85b6-106">Member</span><span class="sxs-lookup"><span data-stu-id="d85b6-106">Member</span></span>|<span data-ttu-id="d85b6-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d85b6-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="d85b6-108">Non è stata impostata alcuna opzione speciale.</span><span class="sxs-lookup"><span data-stu-id="d85b6-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d85b6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d85b6-109">Requirements</span></span>  
 <span data-ttu-id="d85b6-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d85b6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d85b6-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d85b6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d85b6-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d85b6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d85b6-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d85b6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d85b6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d85b6-114">See also</span></span>

- [<span data-ttu-id="d85b6-115">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="d85b6-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
