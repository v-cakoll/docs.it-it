---
title: Interfaccia ICLRProbingAssemblyEnum
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
ms.openlocfilehash: e1459c1604f3f8f043fd9b61533235ab7861c910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120554"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="23c18-102">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="23c18-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="23c18-103">Fornisce metodi che consentono all'host di ottenere le identità di probe di un assembly usando le informazioni sull'identità dell'assembly interne al Common Language Runtime (CLR), senza dover creare o comprendere tale identità.</span><span class="sxs-lookup"><span data-stu-id="23c18-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23c18-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="23c18-104">Methods</span></span>  
  
|<span data-ttu-id="23c18-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="23c18-105">Method</span></span>|<span data-ttu-id="23c18-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="23c18-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23c18-107">Metodo Get</span><span class="sxs-lookup"><span data-stu-id="23c18-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="23c18-108">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="23c18-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23c18-109">Note</span><span class="sxs-lookup"><span data-stu-id="23c18-109">Remarks</span></span>  
 <span data-ttu-id="23c18-110">I metodi, ad esempio [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , restituiscono un'istanza di `ICLRProbingAssemblyEnum`.</span><span class="sxs-lookup"><span data-stu-id="23c18-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="23c18-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="23c18-111">Requirements</span></span>  
 <span data-ttu-id="23c18-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23c18-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23c18-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="23c18-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="23c18-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="23c18-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23c18-115">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23c18-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23c18-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="23c18-116">See also</span></span>

- [<span data-ttu-id="23c18-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="23c18-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="23c18-118">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="23c18-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="23c18-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="23c18-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
