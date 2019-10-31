---
title: Metodo IAppDomainBinding::OnAppDomain
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
ms.openlocfilehash: 37c02b878cd52034603ab6cafe4d8aaca594cbe9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126879"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="aeab3-102">Metodo IAppDomainBinding::OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="aeab3-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="aeab3-103">Chiamato dal Common Language Runtime (CLR) per notificare all'host che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="aeab3-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aeab3-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="aeab3-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aeab3-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="aeab3-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="aeab3-106">in Puntatore a un oggetto dell'interfaccia [IUnknown](/cpp/atl/iunknown) che rappresenta il nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="aeab3-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aeab3-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="aeab3-107">Requirements</span></span>  
 <span data-ttu-id="aeab3-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aeab3-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aeab3-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="aeab3-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="aeab3-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="aeab3-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="aeab3-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aeab3-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aeab3-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="aeab3-112">See also</span></span>

- [<span data-ttu-id="aeab3-113">Interfaccia IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="aeab3-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
