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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c51ddae6aa62552bac9990b57a173c28f73bae5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436832"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="d78ba-102">Metodo ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="d78ba-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="d78ba-103">Ottiene un oggetto che consente all'host specificare la configurazione di callback di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d78ba-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d78ba-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d78ba-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d78ba-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d78ba-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="d78ba-106">[out] Un puntatore all'indirizzo di un [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) oggetto che può essere usato per configurare CLR.</span><span class="sxs-lookup"><span data-stu-id="d78ba-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d78ba-107">Note</span><span class="sxs-lookup"><span data-stu-id="d78ba-107">Remarks</span></span>  
 <span data-ttu-id="d78ba-108">CLR deve essere configurato prima dell'inizializzazione; in caso contrario, il `GetConfiguration` metodo restituisce un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="d78ba-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d78ba-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d78ba-109">Requirements</span></span>  
 <span data-ttu-id="d78ba-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d78ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d78ba-111">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="d78ba-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d78ba-112">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d78ba-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d78ba-113">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="d78ba-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d78ba-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d78ba-114">See Also</span></span>  
 [<span data-ttu-id="d78ba-115">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="d78ba-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
