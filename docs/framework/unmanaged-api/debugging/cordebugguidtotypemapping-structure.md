---
title: Struttura CorDebugGuidToTypeMapping
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: CorDebugGuidToTypeMapping
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugGuidToTypeMapping
helpviewer_keywords: CorDebugGuidToTypeMapping structure [.NET Framework debugging]
ms.assetid: 57dbccd9-b16d-4da3-ae25-7a2cf9adf679
topic_type: apiref
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e4c829f4a74c3d2e84a070dfbe5d35d89b1b7ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="0b9ef-102">Struttura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="0b9ef-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="0b9ef-103">Mappe un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="0b9ef-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0b9ef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0b9ef-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="0b9ef-105">Membri</span><span class="sxs-lookup"><span data-stu-id="0b9ef-105">Members</span></span>  
  
|<span data-ttu-id="0b9ef-106">Membro</span><span class="sxs-lookup"><span data-stu-id="0b9ef-106">Member</span></span>|<span data-ttu-id="0b9ef-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0b9ef-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="0b9ef-108">Il GUID del memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="0b9ef-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="0b9ef-109">Un puntatore a un oggetto ICorDebugType che fornisce informazioni relative al tipo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="0b9ef-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0b9ef-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0b9ef-110">Requirements</span></span>  
 <span data-ttu-id="0b9ef-111">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0b9ef-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="0b9ef-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="0b9ef-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0b9ef-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0b9ef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0b9ef-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0b9ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9ef-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0b9ef-115">See Also</span></span>  
 [<span data-ttu-id="0b9ef-116">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="0b9ef-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="0b9ef-117">Debug</span><span class="sxs-lookup"><span data-stu-id="0b9ef-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
