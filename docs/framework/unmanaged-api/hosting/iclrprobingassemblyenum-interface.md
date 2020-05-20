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
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703380"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="4889e-102">Interfaccia ICLRProbingAssemblyEnum</span><span class="sxs-lookup"><span data-stu-id="4889e-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="4889e-103">Fornisce metodi che consentono all'host di ottenere le identità di probe di un assembly usando le informazioni sull'identità dell'assembly interne al Common Language Runtime (CLR), senza dover creare o comprendere tale identità.</span><span class="sxs-lookup"><span data-stu-id="4889e-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4889e-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="4889e-104">Methods</span></span>  
  
|<span data-ttu-id="4889e-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="4889e-105">Method</span></span>|<span data-ttu-id="4889e-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4889e-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4889e-107">Metodo Get</span><span class="sxs-lookup"><span data-stu-id="4889e-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="4889e-108">Ottiene l'identità dell'assembly in corrispondenza dell'indice specificato.</span><span class="sxs-lookup"><span data-stu-id="4889e-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4889e-109">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4889e-109">Remarks</span></span>  
 <span data-ttu-id="4889e-110">I metodi, ad esempio [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) , restituiscono un' `ICLRProbingAssemblyEnum` istanza di.</span><span class="sxs-lookup"><span data-stu-id="4889e-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4889e-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4889e-111">Requirements</span></span>  
 <span data-ttu-id="4889e-112">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4889e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4889e-113">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4889e-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4889e-114">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4889e-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4889e-115">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4889e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4889e-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4889e-116">See also</span></span>

- [<span data-ttu-id="4889e-117">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="4889e-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4889e-118">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="4889e-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4889e-119">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4889e-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
