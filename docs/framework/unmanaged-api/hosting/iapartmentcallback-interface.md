---
title: Interfaccia IApartmentCallback
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IApartmentCallback
helpviewer_keywords: IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d2f2ea73da2273ff6f0abb725ec3e3fb8ca79ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="8947d-102">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="8947d-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="8947d-103">Fornisce metodi per eseguire callback all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="8947d-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="8947d-104">Un *apartment* è un contenitore logico all'interno di un processo per gli oggetti che condividono gli stessi requisiti di accesso di thread.</span><span class="sxs-lookup"><span data-stu-id="8947d-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8947d-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="8947d-105">Methods</span></span>  
  
|<span data-ttu-id="8947d-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="8947d-106">Method</span></span>|<span data-ttu-id="8947d-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8947d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8947d-108">DoCallback (metodo)</span><span class="sxs-lookup"><span data-stu-id="8947d-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="8947d-109">Esegue la funzione specificata all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="8947d-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8947d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8947d-110">Requirements</span></span>  
 <span data-ttu-id="8947d-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8947d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8947d-112">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8947d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8947d-113">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8947d-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8947d-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8947d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8947d-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8947d-115">See Also</span></span>  
 [<span data-ttu-id="8947d-116">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="8947d-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
