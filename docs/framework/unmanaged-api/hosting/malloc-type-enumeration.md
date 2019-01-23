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
ms.openlocfilehash: 97aded59f880412a6a26e7e3d664c50ff1c2f103
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557409"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="57773-102">Enumerazione MALLOC_TYPE</span><span class="sxs-lookup"><span data-stu-id="57773-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="57773-103">Contiene valori che specificano le caratteristiche della memoria viene allocata.</span><span class="sxs-lookup"><span data-stu-id="57773-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57773-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="57773-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="57773-105">Membri</span><span class="sxs-lookup"><span data-stu-id="57773-105">Members</span></span>  
  
|<span data-ttu-id="57773-106">Membro</span><span class="sxs-lookup"><span data-stu-id="57773-106">Member</span></span>|<span data-ttu-id="57773-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="57773-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="57773-108">La memoria allocata può contenere un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="57773-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="57773-109">La memoria allocata è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="57773-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="57773-110">Vale a dire, la memoria sono accessibili da più thread senza alcuna sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="57773-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="57773-111">Se questo flag non è impostato, le chiamate per l'oggetto devono essere serializzate.</span><span class="sxs-lookup"><span data-stu-id="57773-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="57773-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="57773-112">Requirements</span></span>  
 <span data-ttu-id="57773-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57773-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57773-114">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="57773-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="57773-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57773-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="57773-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57773-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57773-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="57773-117">See also</span></span>
- [<span data-ttu-id="57773-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="57773-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
