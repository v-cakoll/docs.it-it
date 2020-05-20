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
ms.openlocfilehash: f1aa40ef868bf6ff7730e01ab66a6fec58af1196
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615878"
---
# <a name="iclrassemblyreferencelist-interface"></a><span data-ttu-id="73cb3-102">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="73cb3-102">ICLRAssemblyReferenceList Interface</span></span>
<span data-ttu-id="73cb3-103">Gestisce un elenco di assembly caricati dal Common Language Runtime (CLR) e non dall'host.</span><span class="sxs-lookup"><span data-stu-id="73cb3-103">Manages a list of assemblies that are loaded by the common language runtime (CLR) and not by the host.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="73cb3-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="73cb3-104">Methods</span></span>  
  
|<span data-ttu-id="73cb3-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="73cb3-105">Method</span></span>|<span data-ttu-id="73cb3-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73cb3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="73cb3-107">Metodo IsAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="73cb3-107">IsAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isassemblyreferenceinlist-method.md)|<span data-ttu-id="73cb3-108">Ottiene un valore che indica se il puntatore fornito fa riferimento a un assembly presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="73cb3-108">Gets a value that indicates whether the supplied pointer references an assembly in the list.</span></span>|  
|[<span data-ttu-id="73cb3-109">Metodo IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="73cb3-109">IsStringAssemblyReferenceInList Method</span></span>](iclrassemblyreferencelist-isstringassemblyreferenceinlist-method.md)|<span data-ttu-id="73cb3-110">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="73cb3-110">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="73cb3-111">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="73cb3-111">Remarks</span></span>  
 <span data-ttu-id="73cb3-112">Chiamare il metodo [ICLRAssemblyIdentityManager:: GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) per ottenere un puntatore a un'istanza di `ICLRAssemblyReferenceList` .</span><span class="sxs-lookup"><span data-stu-id="73cb3-112">Call the [ICLRAssemblyIdentityManager::GetCLRAssemblyReferenceList](iclrassemblyidentitymanager-getclrassemblyreferencelist-method.md) method to get a pointer to an instance of `ICLRAssemblyReferenceList`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="73cb3-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="73cb3-113">Requirements</span></span>  
 <span data-ttu-id="73cb3-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="73cb3-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="73cb3-115">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="73cb3-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="73cb3-116">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="73cb3-116">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="73cb3-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="73cb3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73cb3-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="73cb3-118">See also</span></span>

- [<span data-ttu-id="73cb3-119">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="73cb3-119">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="73cb3-120">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="73cb3-120">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="73cb3-121">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="73cb3-121">Hosting Interfaces</span></span>](hosting-interfaces.md)
