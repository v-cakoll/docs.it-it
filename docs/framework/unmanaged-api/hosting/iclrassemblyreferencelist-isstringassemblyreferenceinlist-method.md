---
title: Metodo ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
ms.date: 03/30/2017
api_name:
- ICLRAssemblyReferenceList.IsStringAssemblyReferenceInList
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList
helpviewer_keywords:
- ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList method [.NET Framework hosting]
- IsStringAssemblyReferenceInList method [.NET Framework hosting]
ms.assetid: e6121cc3-2f11-42c7-bdae-47808581ff71
topic_type:
- apiref
ms.openlocfilehash: 91f174cab4986882df795eb531baedfc0dd43962
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615865"
---
# <a name="iclrassemblyreferencelistisstringassemblyreferenceinlist-method"></a><span data-ttu-id="ac0a9-102">Metodo ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList</span><span class="sxs-lookup"><span data-stu-id="ac0a9-102">ICLRAssemblyReferenceList::IsStringAssemblyReferenceInList Method</span></span>
<span data-ttu-id="ac0a9-103">Ottiene un valore che indica se il nome fornito corrisponde al nome di un assembly nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-103">Gets a value that indicates whether the supplied name matches the name of an assembly in the list.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac0a9-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac0a9-104">Syntax</span></span>  
  
```cpp  
HRESULT IsStringAssemblyReferenceInList (  
    [in] LPCWSTR pwzAssemblyName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac0a9-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac0a9-105">Parameters</span></span>  
 `pwzAssemblyName`  
 <span data-ttu-id="ac0a9-106">in Nome dell'assembly per il quale eseguire la ricerca.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-106">[in] The name of the assembly for which to search.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ac0a9-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ac0a9-107">Return Value</span></span>  
  
|<span data-ttu-id="ac0a9-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac0a9-108">HRESULT</span></span>|<span data-ttu-id="ac0a9-109">Description</span><span class="sxs-lookup"><span data-stu-id="ac0a9-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac0a9-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac0a9-110">S_OK</span></span>|<span data-ttu-id="ac0a9-111">La stringa viene visualizzata nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-111">The string appears in the list.</span></span>|  
|<span data-ttu-id="ac0a9-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ac0a9-112">S_FALSE</span></span>|<span data-ttu-id="ac0a9-113">La stringa non è presente nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-113">The string does not appear in the list.</span></span>|  
|<span data-ttu-id="ac0a9-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac0a9-114">E_FAIL</span></span>|<span data-ttu-id="ac0a9-115">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-115">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac0a9-116">Dopo che un metodo restituisce E_FAIL, il Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-116">After a method returns E_FAIL, the common language runtime is no longer usable within the process.</span></span> <span data-ttu-id="ac0a9-117">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac0a9-117">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac0a9-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac0a9-118">Requirements</span></span>  
 <span data-ttu-id="ac0a9-119">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac0a9-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac0a9-120">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ac0a9-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac0a9-121">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ac0a9-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac0a9-122">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac0a9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac0a9-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac0a9-123">See also</span></span>

- [<span data-ttu-id="ac0a9-124">Interfaccia ICLRAssemblyIdentityManager</span><span class="sxs-lookup"><span data-stu-id="ac0a9-124">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="ac0a9-125">Interfaccia ICLRAssemblyReferenceList</span><span class="sxs-lookup"><span data-stu-id="ac0a9-125">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="ac0a9-126">Interfaccia IHostAssemblyManager</span><span class="sxs-lookup"><span data-stu-id="ac0a9-126">IHostAssemblyManager Interface</span></span>](ihostassemblymanager-interface.md)
- [<span data-ttu-id="ac0a9-127">Interfaccia IHostAssemblyStore</span><span class="sxs-lookup"><span data-stu-id="ac0a9-127">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
