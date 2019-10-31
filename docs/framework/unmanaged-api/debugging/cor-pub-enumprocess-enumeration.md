---
title: Enumerazione COR_PUB_ENUMPROCESS
ms.date: 03/30/2017
api_name:
- COR_PUB_ENUMPROCESS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_PUB_ENUMPROCESS
helpviewer_keywords:
- COR_PUB_ENUMPROCESS enumeration [.NET Framework debugging]
ms.assetid: 5d3ada6e-feea-47da-a7ed-b664107c137f
topic_type:
- apiref
ms.openlocfilehash: f789105751ae2d498740ab60f326f9c0597483b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73099203"
---
# <a name="cor_pub_enumprocess-enumeration"></a><span data-ttu-id="ccb49-102">Enumerazione COR_PUB_ENUMPROCESS</span><span class="sxs-lookup"><span data-stu-id="ccb49-102">COR_PUB_ENUMPROCESS Enumeration</span></span>
<span data-ttu-id="ccb49-103">Identifica il tipo di processo da enumerare.</span><span class="sxs-lookup"><span data-stu-id="ccb49-103">Identifies the type of process to be enumerated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ccb49-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ccb49-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PUB_MANAGEDONLY    = 0x00000001  
} COR_PUB_ENUMPROCESS;  
```  
  
## <a name="members"></a><span data-ttu-id="ccb49-105">Members</span><span class="sxs-lookup"><span data-stu-id="ccb49-105">Members</span></span>  
  
|<span data-ttu-id="ccb49-106">Nome del membro</span><span class="sxs-lookup"><span data-stu-id="ccb49-106">Member name</span></span>|<span data-ttu-id="ccb49-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ccb49-107">Description</span></span>|  
|-----------------|-----------------|  
|`COR_PUB_MANAGEDONLY`|<span data-ttu-id="ccb49-108">Un processo gestito.</span><span class="sxs-lookup"><span data-stu-id="ccb49-108">A managed process.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ccb49-109">Note</span><span class="sxs-lookup"><span data-stu-id="ccb49-109">Remarks</span></span>  
 <span data-ttu-id="ccb49-110">La versione corrente dell'API di debug non gestito enumera solo i processi gestiti.</span><span class="sxs-lookup"><span data-stu-id="ccb49-110">The current version of the unmanaged debugging API enumerates only managed processes.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ccb49-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ccb49-111">Requirements</span></span>  
 <span data-ttu-id="ccb49-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ccb49-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ccb49-113">**Intestazione:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="ccb49-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="ccb49-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ccb49-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ccb49-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ccb49-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ccb49-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccb49-116">See also</span></span>

- [<span data-ttu-id="ccb49-117">Enumerazioni di debug</span><span class="sxs-lookup"><span data-stu-id="ccb49-117">Debugging Enumerations</span></span>](debugging-enumerations.md)
