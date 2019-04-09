---
title: Interfaccia IApartmentCallback
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db933716cc0602ecda5da8a72726408ae4910179
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129805"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="5d755-102">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="5d755-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="5d755-103">Fornisce metodi per rendere i callback all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="5d755-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="5d755-104">Un' *apartment* è un contenitore logico in un processo per gli oggetti che condividono gli stessi requisiti di accesso di thread.</span><span class="sxs-lookup"><span data-stu-id="5d755-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5d755-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="5d755-105">Methods</span></span>  
  
|<span data-ttu-id="5d755-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="5d755-106">Method</span></span>|<span data-ttu-id="5d755-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5d755-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5d755-108">Metodo DoCallback</span><span class="sxs-lookup"><span data-stu-id="5d755-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="5d755-109">Esegue la funzione specificata all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="5d755-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5d755-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5d755-110">Requirements</span></span>  
 <span data-ttu-id="5d755-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d755-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d755-112">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5d755-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5d755-113">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="5d755-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="5d755-114">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5d755-114">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5d755-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5d755-115">See also</span></span>

- [<span data-ttu-id="5d755-116">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="5d755-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
