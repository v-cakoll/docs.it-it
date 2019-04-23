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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ae3ba480e208762f5a80f9f1b78dd008f02b6df4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59089381"
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="b942f-102">Enumerazione CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="b942f-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="b942f-103">Fornisce opzioni aggiuntive di debug che possono essere utilizzate in una chiamata ai [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="b942f-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b942f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b942f-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="b942f-105">Membri</span><span class="sxs-lookup"><span data-stu-id="b942f-105">Members</span></span>  
  
|<span data-ttu-id="b942f-106">Member</span><span class="sxs-lookup"><span data-stu-id="b942f-106">Member</span></span>|<span data-ttu-id="b942f-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="b942f-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="b942f-108">È impostata alcuna opzione speciale.</span><span class="sxs-lookup"><span data-stu-id="b942f-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b942f-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b942f-109">Requirements</span></span>  
 <span data-ttu-id="b942f-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b942f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b942f-111">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b942f-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b942f-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b942f-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b942f-113">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b942f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b942f-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b942f-114">See also</span></span>

- [<span data-ttu-id="b942f-115">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="b942f-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
