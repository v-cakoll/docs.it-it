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
ms.openlocfilehash: ffa06fd42b5cfa09817bae9f0b3a3810e30f99c4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33430967"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="6da63-102">Interfaccia IApartmentCallback</span><span class="sxs-lookup"><span data-stu-id="6da63-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="6da63-103">Fornisce metodi per eseguire callback all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="6da63-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="6da63-104">Un *apartment* è un contenitore logico all'interno di un processo per gli oggetti che condividono gli stessi requisiti di accesso di thread.</span><span class="sxs-lookup"><span data-stu-id="6da63-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="6da63-105">Metodi</span><span class="sxs-lookup"><span data-stu-id="6da63-105">Methods</span></span>  
  
|<span data-ttu-id="6da63-106">Metodo</span><span class="sxs-lookup"><span data-stu-id="6da63-106">Method</span></span>|<span data-ttu-id="6da63-107">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6da63-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="6da63-108">Metodo DoCallback</span><span class="sxs-lookup"><span data-stu-id="6da63-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="6da63-109">Esegue la funzione specificata all'interno di un apartment.</span><span class="sxs-lookup"><span data-stu-id="6da63-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6da63-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6da63-110">Requirements</span></span>  
 <span data-ttu-id="6da63-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6da63-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6da63-112">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="6da63-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6da63-113">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6da63-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6da63-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6da63-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6da63-115">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6da63-115">See Also</span></span>  
 [<span data-ttu-id="6da63-116">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="6da63-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
