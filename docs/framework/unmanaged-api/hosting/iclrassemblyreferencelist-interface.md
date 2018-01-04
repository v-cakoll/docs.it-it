---
title: Interfaccia ICLRAssemblyReferenceList
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRAssemblyReferenceList
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRAssemblyReferenceList
helpviewer_keywords: ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: eeef0e7f825f4a6ad907d6b17b92afe1807bad12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="e9bf7-102">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="e9bf7-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="e9bf7-103">Gestisce un elenco di assembly caricati da common language runtime (CLR) e non dall'host.</span><span class="sxs-lookup"><span data-stu-id="e9bf7-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e9bf7-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="e9bf7-104">Methods</span></span>  
  
|<span data-ttu-id="e9bf7-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="e9bf7-105">Method</span></span>|<span data-ttu-id="e9bf7-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9bf7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="e9bf7-107">Metodo IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="e9bf7-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="e9bf7-108">Ottiene un valore che indica se il puntatore fornito fa riferimento a un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e9bf7-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="e9bf7-109">Metodo IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="e9bf7-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="e9bf7-110">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e9bf7-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9bf7-111">Note</span><span class="sxs-lookup"><span data-stu-id="e9bf7-111">Remarks</span></span>  
 <span data-ttu-id="e9bf7-112">Chiamare il [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) metodo per ottenere un puntatore a un'istanza di `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="e9bf7-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9bf7-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e9bf7-113">Requirements</span></span>  
 <span data-ttu-id="e9bf7-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9bf7-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9bf7-115">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="e9bf7-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9bf7-116">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9bf7-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9bf7-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9bf7-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9bf7-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e9bf7-118">See Also</span></span>  
 [<span data-ttu-id="e9bf7-119">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="e9bf7-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="e9bf7-120">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="e9bf7-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)  
 [<span data-ttu-id="e9bf7-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="e9bf7-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
