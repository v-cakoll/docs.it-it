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
ms.openlocfilehash: e74d49d71cfee51f8cb99645151aace3d02de0e8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126657"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="c57ef-102">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="c57ef-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="c57ef-103">Gestisce un elenco di assembly caricati dal Common Language Runtime (CLR) e non dall'host.</span><span class="sxs-lookup"><span data-stu-id="c57ef-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c57ef-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="c57ef-104">Methods</span></span>  
  
|<span data-ttu-id="c57ef-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="c57ef-105">Method</span></span>|<span data-ttu-id="c57ef-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c57ef-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c57ef-107">Metodo IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="c57ef-107">IsAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="c57ef-108">Ottiene un valore che indica se il puntatore fornito fa riferimento a un assembly presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c57ef-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="c57ef-109">Metodo IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="c57ef-109">IsStringAssemblyReferenceInList Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="c57ef-110">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c57ef-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c57ef-111">Note</span><span class="sxs-lookup"><span data-stu-id="c57ef-111">Remarks</span></span>  
 <span data-ttu-id="c57ef-112">Chiamare il metodo [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) per ottenere un puntatore a un'istanza di `ICLRAssemblyReferenceList`.</span><span class="sxs-lookup"><span data-stu-id="c57ef-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c57ef-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c57ef-113">Requirements</span></span>  
 <span data-ttu-id="c57ef-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c57ef-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c57ef-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c57ef-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c57ef-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c57ef-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c57ef-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c57ef-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c57ef-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c57ef-118">See also</span></span>

- [<span data-ttu-id="c57ef-119">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="c57ef-119">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="c57ef-120">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="c57ef-120">IHostAssemblyStore Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
- [<span data-ttu-id="c57ef-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="c57ef-121">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
