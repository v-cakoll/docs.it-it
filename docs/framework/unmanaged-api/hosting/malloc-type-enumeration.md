---
title: Enumerazione MALLOC_TYPE
ms.date: 03/30/2017
api_name:
- MALLOC_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MALLOC_TYPE
helpviewer_keywords:
- MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 695f69c8d9c3a295a705971743733339cf8aab13
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59211946"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="d6aef-102">Enumerazione MALLOC_TYPE</span><span class="sxs-lookup"><span data-stu-id="d6aef-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="d6aef-103">Contiene valori che specificano le caratteristiche della memoria viene allocata.</span><span class="sxs-lookup"><span data-stu-id="d6aef-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6aef-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d6aef-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="d6aef-105">Membri</span><span class="sxs-lookup"><span data-stu-id="d6aef-105">Members</span></span>  
  
|<span data-ttu-id="d6aef-106">Member</span><span class="sxs-lookup"><span data-stu-id="d6aef-106">Member</span></span>|<span data-ttu-id="d6aef-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d6aef-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="d6aef-108">La memoria allocata può contenere un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="d6aef-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="d6aef-109">La memoria allocata è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="d6aef-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="d6aef-110">Vale a dire, la memoria sono accessibili da più thread senza alcuna sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="d6aef-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="d6aef-111">Se questo flag non è impostato, le chiamate per l'oggetto devono essere serializzate.</span><span class="sxs-lookup"><span data-stu-id="d6aef-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6aef-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d6aef-112">Requirements</span></span>  
 <span data-ttu-id="d6aef-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6aef-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6aef-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d6aef-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6aef-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d6aef-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6aef-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6aef-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6aef-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d6aef-117">See also</span></span>

- [<span data-ttu-id="d6aef-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="d6aef-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
