---
title: Struttura CorDebugGuidToTypeMapping
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- cpp
api_name:
- CorDebugGuidToTypeMapping
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugGuidToTypeMapping
helpviewer_keywords:
- CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: ecdadc96c0fb850fef13ba978fc97eef91dadd65
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="89c24-102">Struttura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="89c24-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="89c24-103">Mappe un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="89c24-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89c24-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="89c24-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="89c24-105">Membri</span><span class="sxs-lookup"><span data-stu-id="89c24-105">Members</span></span>  
  
|<span data-ttu-id="89c24-106">Membro</span><span class="sxs-lookup"><span data-stu-id="89c24-106">Member</span></span>|<span data-ttu-id="89c24-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="89c24-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="89c24-108">Il GUID del memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="89c24-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="89c24-109">Un puntatore a un oggetto ICorDebugType che fornisce informazioni relative al tipo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="89c24-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="89c24-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="89c24-110">Requirements</span></span>  
 <span data-ttu-id="89c24-111">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="89c24-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="89c24-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="89c24-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89c24-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89c24-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89c24-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89c24-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89c24-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="89c24-115">See Also</span></span>  
 [<span data-ttu-id="89c24-116">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="89c24-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="89c24-117">Debug</span><span class="sxs-lookup"><span data-stu-id="89c24-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
