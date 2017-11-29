---
title: Enumerazione MALLOC_TYPE
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: MALLOC_TYPE
api_location: mscoree.dll
api_type: COM
f1_keywords: MALLOC_TYPE
helpviewer_keywords: MALLOC_TYPE Enumeration
ms.assetid: c02476f9-23a2-4af7-9282-aa9c42c7429b
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 59a379b1c34f5b7c6b721627e6053cacf3ed784a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="malloctype-enumeration"></a><span data-ttu-id="a78ee-102">Enumerazione MALLOC_TYPE</span><span class="sxs-lookup"><span data-stu-id="a78ee-102">MALLOC_TYPE Enumeration</span></span>
<span data-ttu-id="a78ee-103">Contiene valori che specificano le caratteristiche della memoria allocata.</span><span class="sxs-lookup"><span data-stu-id="a78ee-103">Contains values that specify the characteristics of the memory that is being allocated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a78ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a78ee-104">Syntax</span></span>  
  
```  
typedef enum {  
    MALLOC_THREADSAFE = 0x1,  
    MALLOC_EXECUTABLE = 0x2,  
} MALLOC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="a78ee-105">Membri</span><span class="sxs-lookup"><span data-stu-id="a78ee-105">Members</span></span>  
  
|<span data-ttu-id="a78ee-106">Membro</span><span class="sxs-lookup"><span data-stu-id="a78ee-106">Member</span></span>|<span data-ttu-id="a78ee-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="a78ee-107">Description</span></span>|  
|------------|-----------------|  
|`MALLOC_EXECUTABLE`|<span data-ttu-id="a78ee-108">La memoria allocata può contenere un file eseguibile.</span><span class="sxs-lookup"><span data-stu-id="a78ee-108">The allocated memory can contain an executable file.</span></span>|  
|`MALLOC_THREADSAFE`|<span data-ttu-id="a78ee-109">La memoria allocata è thread-safe.</span><span class="sxs-lookup"><span data-stu-id="a78ee-109">The allocated memory is thread-safe.</span></span> <span data-ttu-id="a78ee-110">Ovvero, la memoria sono accessibili da più thread senza alcuna sincronizzazione.</span><span class="sxs-lookup"><span data-stu-id="a78ee-110">That is, the memory can be accessed by multiple threads without any synchronization.</span></span><br /><br /> <span data-ttu-id="a78ee-111">Se questo flag non è impostato, le chiamate per l'oggetto devono essere serializzate.</span><span class="sxs-lookup"><span data-stu-id="a78ee-111">If this flag is not set, calls on the object must be serialized.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a78ee-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a78ee-112">Requirements</span></span>  
 <span data-ttu-id="a78ee-113">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a78ee-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a78ee-114">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="a78ee-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a78ee-115">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a78ee-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a78ee-116">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a78ee-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a78ee-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a78ee-117">See Also</span></span>  
 [<span data-ttu-id="a78ee-118">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="a78ee-118">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
