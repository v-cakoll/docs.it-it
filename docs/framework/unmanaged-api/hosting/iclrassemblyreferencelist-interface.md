---
title: Interfaccia ICLRAssemblyReferenceList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList
helpviewer_keywords:
- ICLRAssemblyReferenceList interface [.NET Framework hosting]
ms.assetid: 5f890fdf-d22a-429e-a35f-135273d1a636
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1c2b383abdc67546749867de154a00fda244b3ad
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660021"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="249a6-102">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="249a6-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="249a6-103">Gestisce un elenco di assembly caricati da common language runtime (CLR) e non dall'host.</span><span class="sxs-lookup"><span data-stu-id="249a6-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="249a6-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="249a6-104">Methods</span></span>  
  
|<span data-ttu-id="249a6-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="249a6-105">Method</span></span>|<span data-ttu-id="249a6-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="249a6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="249a6-107">Metodo IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="249a6-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="249a6-108">Ottiene un valore che indica se il puntatore fornito fa riferimento a un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="249a6-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="249a6-109">Metodo IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="249a6-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="249a6-110">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="249a6-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="249a6-111">Note</span><span class="sxs-lookup"><span data-stu-id="249a6-111">Remarks</span></span>  
 <span data-ttu-id="249a6-112">Chiamare il [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) metodo per ottenere un puntatore a un'istanza di `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="249a6-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249a6-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="249a6-113">Requirements</span></span>  
 <span data-ttu-id="249a6-114">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="249a6-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249a6-115">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="249a6-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="249a6-116">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="249a6-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="249a6-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249a6-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="249a6-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="249a6-118">See also</span></span>
- [<span data-ttu-id="249a6-119">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="249a6-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="249a6-120">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="249a6-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="249a6-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="249a6-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
