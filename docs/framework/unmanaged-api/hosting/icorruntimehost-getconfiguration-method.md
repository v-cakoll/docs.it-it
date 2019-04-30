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
ms.openlocfilehash: cf74da6eb0e7ce0215023a9a58d6b88c57c4fe8b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936942"
---
# <a name="icorruntimehostgetconfiguration-method"></a><span data-ttu-id="dbd69-102">Metodo ICorRuntimeHost::GetConfiguration</span><span class="sxs-lookup"><span data-stu-id="dbd69-102">ICorRuntimeHost::GetConfiguration Method</span></span>
<span data-ttu-id="dbd69-103">Ottiene un oggetto che consente all'host specificare la configurazione di callback di common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="dbd69-103">Gets an object that allows the host to specify the callback configuration of the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dbd69-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dbd69-104">Syntax</span></span>  
  
```  
HRESULT GetConfiguration(  
    [out] ICorConfiguration** pConfiguration  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dbd69-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dbd69-105">Parameters</span></span>  
 `pConfiguration`  
 <span data-ttu-id="dbd69-106">[out] Un puntatore all'indirizzo di un [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) oggetto che può essere usato per configurare il CLR.</span><span class="sxs-lookup"><span data-stu-id="dbd69-106">[out] A pointer to the address of an [ICorConfiguration](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md) object that can be used to configure the CLR.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dbd69-107">Note</span><span class="sxs-lookup"><span data-stu-id="dbd69-107">Remarks</span></span>  
 <span data-ttu-id="dbd69-108">CLR deve essere configurato prima dell'inizializzazione; in caso contrario, il `GetConfiguration` metodo restituisce un HRESULT che indica un errore.</span><span class="sxs-lookup"><span data-stu-id="dbd69-108">The CLR must be configured prior to its initialization; otherwise, the `GetConfiguration` method returns an HRESULT indicating an error.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dbd69-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dbd69-109">Requirements</span></span>  
 <span data-ttu-id="dbd69-110">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbd69-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbd69-111">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="dbd69-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="dbd69-112">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="dbd69-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="dbd69-113">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="dbd69-113">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbd69-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="dbd69-114">See also</span></span>

- [<span data-ttu-id="dbd69-115">Interfaccia ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="dbd69-115">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
