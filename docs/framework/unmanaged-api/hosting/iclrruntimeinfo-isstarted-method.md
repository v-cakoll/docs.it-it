---
title: Metodo ICLRRuntimeInfo::IsStarted
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb23a8e4237ff9b4b217458150c1f04956e439ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526592"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="4c06d-102">Metodo ICLRRuntimeInfo::IsStarted</span><span class="sxs-lookup"><span data-stu-id="4c06d-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="4c06d-103">Indica se il runtime è stato avviato (vale a dire, se il [ICLRRuntimeHost::](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) è stato chiamato e ha avuto esito positivo).</span><span class="sxs-lookup"><span data-stu-id="4c06d-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4c06d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4c06d-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4c06d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4c06d-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="4c06d-106">[out] `true` se questa istanza di runtime è avviato; in caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4c06d-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="4c06d-107">[out] Restituisce i flag utilizzati per avviare il runtime.</span><span class="sxs-lookup"><span data-stu-id="4c06d-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4c06d-108">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4c06d-108">Return Value</span></span>  
 <span data-ttu-id="4c06d-109">Questo metodo restituisce gli specifici HRESULT seguenti, nonché gli errori di HRESULT che indicano la mancata riuscita del metodo.</span><span class="sxs-lookup"><span data-stu-id="4c06d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4c06d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4c06d-110">HRESULT</span></span>|<span data-ttu-id="4c06d-111">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4c06d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4c06d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="4c06d-112">S_OK</span></span>|<span data-ttu-id="4c06d-113">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4c06d-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="4c06d-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="4c06d-114">E_NOTIMPL</span></span>|<span data-ttu-id="4c06d-115">La versione di common language runtime (CLR) è precedente alla versione CLR nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c06d-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c06d-116">Note</span><span class="sxs-lookup"><span data-stu-id="4c06d-116">Remarks</span></span>  
 <span data-ttu-id="4c06d-117">Questo metodo non funziona con le versioni CLR precedenti alla versione di CLR nel [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c06d-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c06d-118">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4c06d-118">Requirements</span></span>  
 <span data-ttu-id="4c06d-119">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c06d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c06d-120">**Intestazione:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="4c06d-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="4c06d-121">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="4c06d-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c06d-122">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c06d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c06d-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4c06d-123">See also</span></span>
- [<span data-ttu-id="4c06d-124">Interfaccia ICLRRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="4c06d-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="4c06d-125">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="4c06d-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="4c06d-126">Hosting</span><span class="sxs-lookup"><span data-stu-id="4c06d-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
