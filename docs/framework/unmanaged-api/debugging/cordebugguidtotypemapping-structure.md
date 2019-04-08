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
ms.openlocfilehash: 9dc7093edaf12e801a1e1adc52b0be823ff92b91
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59079916"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="c6ca3-102">Struttura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="c6ca3-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="c6ca3-103">Esegue il mapping un [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID per l'oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c6ca3-103">Maps a [!INCLUDE[wrt](../../../../includes/wrt-md.md)] GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6ca3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6ca3-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="c6ca3-105">Membri</span><span class="sxs-lookup"><span data-stu-id="c6ca3-105">Members</span></span>  
  
|<span data-ttu-id="c6ca3-106">Member</span><span class="sxs-lookup"><span data-stu-id="c6ca3-106">Member</span></span>|<span data-ttu-id="c6ca3-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c6ca3-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="c6ca3-108">Il GUID del memorizzato nella cache [!INCLUDE[wrt](../../../../includes/wrt-md.md)] tipo.</span><span class="sxs-lookup"><span data-stu-id="c6ca3-108">The GUID of the cached [!INCLUDE[wrt](../../../../includes/wrt-md.md)] type.</span></span>|  
|`pType`|<span data-ttu-id="c6ca3-109">Un puntatore a un oggetto ICorDebugType che fornisce informazioni sul tipo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="c6ca3-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6ca3-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6ca3-110">Requirements</span></span>  
 <span data-ttu-id="c6ca3-111">**Piattaforme:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c6ca3-111">**Platforms:** [!INCLUDE[wrt](../../../../includes/wrt-md.md)].</span></span>  
  
 <span data-ttu-id="c6ca3-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6ca3-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6ca3-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6ca3-113">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="c6ca3-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c6ca3-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c6ca3-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6ca3-115">See also</span></span>

- [<span data-ttu-id="c6ca3-116">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="c6ca3-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="c6ca3-117">Debug</span><span class="sxs-lookup"><span data-stu-id="c6ca3-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
