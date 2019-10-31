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
ms.openlocfilehash: 313f6649448653ad630d616c7dbf739653e352dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132832"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="2270e-102">Struttura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="2270e-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="2270e-103">Esegue il mapping di un GUID Windows Runtime al relativo oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="2270e-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2270e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2270e-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="2270e-105">Members</span><span class="sxs-lookup"><span data-stu-id="2270e-105">Members</span></span>  
  
|<span data-ttu-id="2270e-106">Member</span><span class="sxs-lookup"><span data-stu-id="2270e-106">Member</span></span>|<span data-ttu-id="2270e-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2270e-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="2270e-108">GUID del tipo di Windows Runtime memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="2270e-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="2270e-109">Puntatore a un oggetto ICorDebugType che fornisce informazioni sul tipo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="2270e-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2270e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2270e-110">Requirements</span></span>  
 <span data-ttu-id="2270e-111">**Piattaforme:** Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="2270e-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="2270e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2270e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2270e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2270e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2270e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2270e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2270e-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2270e-115">See also</span></span>

- [<span data-ttu-id="2270e-116">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="2270e-116">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="2270e-117">Debug</span><span class="sxs-lookup"><span data-stu-id="2270e-117">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
