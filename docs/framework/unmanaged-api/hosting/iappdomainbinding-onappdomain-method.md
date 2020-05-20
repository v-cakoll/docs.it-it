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
ms.openlocfilehash: 2d5dbd003d0ea5decae0025d47e6bd5c1fb1ed4a
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617074"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="c6838-102">Metodo IAppDomainBinding::OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="c6838-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="c6838-103">Chiamato dal Common Language Runtime (CLR) per notificare all'host che è stato creato un dominio dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6838-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6838-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c6838-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c6838-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c6838-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="c6838-106">in Puntatore a un oggetto dell'interfaccia [IUnknown](/cpp/atl/iunknown) che rappresenta il nuovo dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="c6838-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6838-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c6838-107">Requirements</span></span>  
 <span data-ttu-id="c6838-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6838-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6838-109">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="c6838-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6838-110">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c6838-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6838-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6838-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6838-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c6838-112">See also</span></span>

- [<span data-ttu-id="c6838-113">Interfaccia IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="c6838-113">IAppDomainBinding Interface</span></span>](iappdomainbinding-interface.md)
