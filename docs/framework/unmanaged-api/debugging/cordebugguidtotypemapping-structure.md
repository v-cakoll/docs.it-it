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
ms.openlocfilehash: b855a53c9e4303138d7605bdf108d37bb345b917
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789335"
---
# <a name="cordebugguidtotypemapping-structure"></a><span data-ttu-id="9ebd4-102">Struttura CorDebugGuidToTypeMapping</span><span class="sxs-lookup"><span data-stu-id="9ebd4-102">CorDebugGuidToTypeMapping Structure</span></span>
<span data-ttu-id="9ebd4-103">Esegue il mapping di un GUID Windows Runtime al relativo oggetto ICorDebugType corrispondente.</span><span class="sxs-lookup"><span data-stu-id="9ebd4-103">Maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ebd4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9ebd4-104">Syntax</span></span>  
  
```cpp
typedef struct CorDebugGuidToTypeMapping {  
    GUID iid;  
    ICorDebugType *pType;  
} CorDebugGuidToTypeMapping;  
```  
  
## <a name="members"></a><span data-ttu-id="9ebd4-105">Membri</span><span class="sxs-lookup"><span data-stu-id="9ebd4-105">Members</span></span>  
  
|<span data-ttu-id="9ebd4-106">Member</span><span class="sxs-lookup"><span data-stu-id="9ebd4-106">Member</span></span>|<span data-ttu-id="9ebd4-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ebd4-107">Description</span></span>|  
|------------|-----------------|  
|`iid`|<span data-ttu-id="9ebd4-108">GUID del tipo di Windows Runtime memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="9ebd4-108">The GUID of the cached Windows Runtime type.</span></span>|  
|`pType`|<span data-ttu-id="9ebd4-109">Puntatore a un oggetto ICorDebugType che fornisce informazioni sul tipo memorizzato nella cache.</span><span class="sxs-lookup"><span data-stu-id="9ebd4-109">A pointer to an ICorDebugType object that provides information about the cached type.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9ebd4-110">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="9ebd4-110">Requirements</span></span>  
 <span data-ttu-id="9ebd4-111">**Piattaforme:** Windows Runtime.</span><span class="sxs-lookup"><span data-stu-id="9ebd4-111">**Platforms:** Windows Runtime.</span></span>  
  
 <span data-ttu-id="9ebd4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9ebd4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9ebd4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9ebd4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9ebd4-114">**Versioni .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9ebd4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ebd4-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9ebd4-115">See also</span></span>

- [<span data-ttu-id="9ebd4-116">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="9ebd4-116">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="9ebd4-117">Debug</span><span class="sxs-lookup"><span data-stu-id="9ebd4-117">Debugging</span></span>](index.md)
