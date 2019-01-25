---
title: Struttura CorDebugGuidToTypeMapping
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 49290a37ca7ea101e3c8b458a5daa4995cb3beee
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54610045"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="f7f5d-102">Struttura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="f7f5d-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="f7f5d-103">Esegue il mapping un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID per l'oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="f7f5d-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7f5d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f7f5d-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="f7f5d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="f7f5d-105">Members</span></span>  
  
|<span data-ttu-id="f7f5d-106">Membro</span><span class="sxs-lookup"><span data-stu-id="f7f5d-106">Member</span></span>|<span data-ttu-id="f7f5d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f7f5d-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="f7f5d-108">Il GUID del memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="f7f5d-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="f7f5d-109">Un puntatore a un oggetto ICorDebugType che fornisce informazioni sul tipo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="f7f5d-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7f5d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f7f5d-110">Requirements</span></span>  
 <span data-ttu-id="f7f5d-111">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7f5d-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="f7f5d-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f7f5d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f7f5d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7f5d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7f5d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7f5d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7f5d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f7f5d-115">See also</span></span>
- [<span data-ttu-id="f7f5d-116">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="f7f5d-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="f7f5d-117">Debug</span><span class="sxs-lookup"><span data-stu-id="f7f5d-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
