---
title: Metodo IAppDomainBinding::OnAppDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IAppDomainBinding.OnAppDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f5350b9c44c04a4faee3b5026bc2b97ff549d4b4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="2e385-102">Metodo IAppDomainBinding::OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="2e385-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="2e385-103">Chiamato da common language runtime (CLR) per notificare all'host che è stato creato un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e385-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e385-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2e385-104">Syntax</span></span>  
  
```  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2e385-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2e385-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="2e385-106">[in] Un puntatore a un [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) oggetto dell'interfaccia che rappresenta il nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="2e385-106">[in] A pointer to an [IUnknown](https://msdn.microsoft.com/library/94as6ehy(v=vs.110).aspx) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2e385-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2e385-107">Requirements</span></span>  
 <span data-ttu-id="2e385-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e385-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e385-109">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="2e385-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2e385-110">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e385-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2e385-111">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e385-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e385-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2e385-112">See Also</span></span>  
 [<span data-ttu-id="2e385-113">IAppDomainBinding (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="2e385-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
