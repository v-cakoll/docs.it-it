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
ms.openlocfilehash: 38e1b19d6340f559e6f8b7e0f7bc042a10df16c3
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025991"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="5116d-102">Struttura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="5116d-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="5116d-103">Esegue il mapping di un GUID di Runtime di Windows per l'oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="5116d-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5116d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5116d-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="5116d-105">Membri</span><span class="sxs-lookup"><span data-stu-id="5116d-105">Members</span></span>  
  
|<span data-ttu-id="5116d-106">Member</span><span class="sxs-lookup"><span data-stu-id="5116d-106">Member</span></span>|<span data-ttu-id="5116d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5116d-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="5116d-108">Il GUID del tipo di Runtime di Windows memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="5116d-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="5116d-109">Un puntatore a un oggetto ICorDebugType che fornisce informazioni sul tipo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="5116d-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5116d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5116d-110">Requirements</span></span>  
 <span data-ttu-id="5116d-111">**Piattaforme:** Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="5116d-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="5116d-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5116d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5116d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5116d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5116d-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5116d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5116d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5116d-115">See also</span></span>

- [<span data-ttu-id="5116d-116">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="5116d-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="5116d-117">Debug</span><span class="sxs-lookup"><span data-stu-id="5116d-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
