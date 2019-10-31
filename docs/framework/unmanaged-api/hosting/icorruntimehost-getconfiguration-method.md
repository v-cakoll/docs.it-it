---
title: Metodo ICorRuntimeHost::GetConfiguration
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.GetConfiguration
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::GetConfiguration
helpviewer_keywords:
- ICorRuntimeHost::GetConfiguration method [.NET Framework hosting]
- GetConfiguration method [.NET Framework hosting]
ms.assetid: c431617a-b055-44a0-8730-48b7a86d9610
topic_type:
- apiref
ms.openlocfilehash: 87549118742da797ef0dd1b08ae9e72c466f7841
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139572"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="610e6-102">Metodo ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="610e6-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="610e6-103">Ottiene un oggetto che consente all'host di specificare la configurazione di callback del Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="610e6-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="610e6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="610e6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="610e6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="610e6-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="610e6-106">out Puntatore all'indirizzo di un oggetto [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) che può essere utilizzato per configurare CLR.</span><span class="sxs-lookup"><span data-stu-id="610e6-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="610e6-107">Note</span><span class="sxs-lookup"><span data-stu-id="610e6-107">Remarks</span></span>  
 <span data-ttu-id="610e6-108">CLR deve essere configurato prima dell'inizializzazione. in caso contrario, il metodo `GetConfiguration` restituisce un valore HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="610e6-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="610e6-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="610e6-109">Requirements</span></span>  
 <span data-ttu-id="610e6-110">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="610e6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="610e6-111">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="610e6-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="610e6-112">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="610e6-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="610e6-113">**Versioni .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="610e6-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="610e6-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="610e6-114">See also</span></span>

- [<span data-ttu-id="610e6-115">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="610e6-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
