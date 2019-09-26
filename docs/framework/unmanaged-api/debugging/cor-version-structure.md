---
title: Struttura COR_VERSION
ms.date: 03/30/2017
api_name:
- COR_VERSION
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_VERSION
helpviewer_keywords:
- COR_VERSION structure [.NET Framework debugging]
ms.assetid: 5efaee1c-a001-4c73-9525-4160f4c71567
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ffbe571ebc3d14c12e57b1f805d77e56e97d12e1
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274178"
---
# <a name="cor_version-structure"></a><span data-ttu-id="3aa5c-102">Struttura COR_VERSION</span><span class="sxs-lookup"><span data-stu-id="3aa5c-102">COR_VERSION Structure</span></span>
<span data-ttu-id="3aa5c-103">Archivia il numero di versione in quattro parti standard di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="3aa5c-103">Stores the standard four-part version number of the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aa5c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3aa5c-104">Syntax</span></span>  
  
```cpp  
typedef struct _COR_VERSION {  
    DWORD dwMajor;  
    DWORD dwMinor;  
    DWORD dwBuild;  
    DWORD dwSubBuild;  
} COR_VERSION;  
```  
  
## <a name="members"></a><span data-ttu-id="3aa5c-105">Membri</span><span class="sxs-lookup"><span data-stu-id="3aa5c-105">Members</span></span>  
  
|<span data-ttu-id="3aa5c-106">Member</span><span class="sxs-lookup"><span data-stu-id="3aa5c-106">Member</span></span>|<span data-ttu-id="3aa5c-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3aa5c-107">Description</span></span>|  
|------------|-----------------|  
|`dwMajor`|<span data-ttu-id="3aa5c-108">Numero di versione principale.</span><span class="sxs-lookup"><span data-stu-id="3aa5c-108">The major version number.</span></span>|  
|`dwMinor`|<span data-ttu-id="3aa5c-109">Numero di versione secondario.</span><span class="sxs-lookup"><span data-stu-id="3aa5c-109">The minor version number.</span></span>|  
|`dwBuild`|<span data-ttu-id="3aa5c-110">Numero di Build.</span><span class="sxs-lookup"><span data-stu-id="3aa5c-110">The build number.</span></span>|  
|`dwSubBuild`|<span data-ttu-id="3aa5c-111">Numero della sottocompilazione.</span><span class="sxs-lookup"><span data-stu-id="3aa5c-111">The sub-build number.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aa5c-112">Note</span><span class="sxs-lookup"><span data-stu-id="3aa5c-112">Remarks</span></span>  
 <span data-ttu-id="3aa5c-113">Se il numero di versione è 1.0.3705.288, 1 è il numero di versione principale, 0 è il numero di versione secondario, 3705 è il numero di build e 288 è il numero di sottocompilazione.</span><span class="sxs-lookup"><span data-stu-id="3aa5c-113">If the version number is 1.0.3705.288, 1 is the major version number, 0 is the minor version number, 3705 is the build number, and 288 is the sub-build number.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3aa5c-114">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3aa5c-114">Requirements</span></span>  
 <span data-ttu-id="3aa5c-115">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3aa5c-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3aa5c-116">**Intestazione:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="3aa5c-116">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="3aa5c-117">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3aa5c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3aa5c-118">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3aa5c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aa5c-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3aa5c-119">See also</span></span>

- [<span data-ttu-id="3aa5c-120">Strutture di debug</span><span class="sxs-lookup"><span data-stu-id="3aa5c-120">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="3aa5c-121">Debug</span><span class="sxs-lookup"><span data-stu-id="3aa5c-121">Debugging</span></span>](index.md)
