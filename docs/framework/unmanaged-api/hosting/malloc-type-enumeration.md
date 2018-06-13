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
ms.openlocfilehash: 2c5e970a1677b1e43821cce9985e32ebd0726686
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442540"
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="13253-102">Enumerazione MALLOC_TYPE</span><span class="sxs-lookup"><span data-stu-id="13253-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="13253-103">Contiene valori che specificano le caratteristiche della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="13253-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13253-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="13253-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="13253-105">Membri</span><span class="sxs-lookup"><span data-stu-id="13253-105">Members</span></span>  
  
|<span data-ttu-id="13253-106">Membro</span><span class="sxs-lookup"><span data-stu-id="13253-106">Member</span></span>|<span data-ttu-id="13253-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="13253-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="13253-108">La memoria allocata può contenere un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="13253-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="13253-109">La memoria allocata è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="13253-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="13253-110">Ovvero, la memoria sono accessibili da più thread senza alcuna sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="13253-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="13253-111">Se questo flag non è impostato, le chiamate per l'oggetto devono essere serializzate.</span><span class="sxs-lookup"><span data-stu-id="13253-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13253-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="13253-112">Requirements</span></span>  
 <span data-ttu-id="13253-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13253-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13253-114">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="13253-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="13253-115">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="13253-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="13253-116">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13253-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13253-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13253-117">See Also</span></span>  
 [<span data-ttu-id="13253-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="13253-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
