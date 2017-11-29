---
title: Enumerazione CorDebugCreateProcessFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugCreateProcessFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugCreateProcessFlags
helpviewer_keywords: CorDebugCreateProcessFlags enumeration [.NET Framework debugging]
ms.assetid: e709acce-6a17-4346-b38a-467dba567358
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35503a89077b05d622ccc3f8e5cf1bb7d95ea9e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="cordebugcreateprocessflags-enumeration"></a><span data-ttu-id="ecd4b-102">Enumerazione CorDebugCreateProcessFlags</span><span class="sxs-lookup"><span data-stu-id="ecd4b-102">CorDebugCreateProcessFlags Enumeration</span></span>
<span data-ttu-id="ecd4b-103">Fornisce opzioni di debug aggiuntive che possono essere utilizzate in una chiamata al [ICorDebug:: CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="ecd4b-103">Provides additional debugging options that can be used in a call to the [ICorDebug::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebug-createprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecd4b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ecd4b-104">Syntax</span></span>  
  
```  
typedef enum CorDebugCreateProcessFlags {  
    DEBUG_NO_SPECIAL_OPTIONS    = 0x0000  
} CorDebugCreateProcessFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ecd4b-105">Membri</span><span class="sxs-lookup"><span data-stu-id="ecd4b-105">Members</span></span>  
  
|<span data-ttu-id="ecd4b-106">Membro</span><span class="sxs-lookup"><span data-stu-id="ecd4b-106">Member</span></span>|<span data-ttu-id="ecd4b-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ecd4b-107">Description</span></span>|  
|------------|-----------------|  
|`DEBUG_NO_SPECIAL_OPTIONS`|<span data-ttu-id="ecd4b-108">Non vengono impostati opzioni speciali.</span><span class="sxs-lookup"><span data-stu-id="ecd4b-108">No special options are set.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ecd4b-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ecd4b-109">Requirements</span></span>  
 <span data-ttu-id="ecd4b-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecd4b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecd4b-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="ecd4b-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ecd4b-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ecd4b-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ecd4b-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecd4b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecd4b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ecd4b-114">See Also</span></span>  
 [<span data-ttu-id="ecd4b-115">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ecd4b-115">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
