---
title: Metodo ICLRValidator::FormatEventInfo
ms.date: 03/30/2017
api_name:
- ICLRValidator.FormatEventInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::FormatEventInfo
helpviewer_keywords:
- FormatEventInfo method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::FormatEventInfo method [.NET Framework hosting]
ms.assetid: 808e1f1d-52f4-47c4-83cc-dcf47d075219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 30fca37887c17f5f0da7fd2faaba32f0e5edf235
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437365"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="bfa3f-102">Metodo ICLRValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="bfa3f-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="bfa3f-103">Ottiene un messaggio dettagliato sull'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfa3f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="bfa3f-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bfa3f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="bfa3f-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="bfa3f-106">[in] Il valore HRESULT passato al gestore di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="bfa3f-107">[in] Oggetto `VEContext` istanza che contiene informazioni sul contesto relative agli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="bfa3f-108">[in, out] Il messaggio di errore descrittivo.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="bfa3f-109">[in] La lunghezza massima del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="bfa3f-110">[in] Una matrice protetta di parametri aggiuntivi da utilizzare nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfa3f-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="bfa3f-111">Return Value</span></span>  
  
|<span data-ttu-id="bfa3f-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bfa3f-112">HRESULT</span></span>|<span data-ttu-id="bfa3f-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bfa3f-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bfa3f-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="bfa3f-114">S_OK</span></span>|<span data-ttu-id="bfa3f-115">`FormatEventInfo` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="bfa3f-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bfa3f-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bfa3f-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bfa3f-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bfa3f-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bfa3f-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-119">The call timed out.</span></span>|  
|<span data-ttu-id="bfa3f-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bfa3f-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bfa3f-121">Il chiamante non dispone del blocco.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bfa3f-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bfa3f-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bfa3f-123">Un evento è stato annullato mentre un thread bloccato o fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bfa3f-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bfa3f-124">E_FAIL</span></span>|<span data-ttu-id="bfa3f-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bfa3f-126">Quando un metodo viene restituito E_FAIL, Common Language Runtime non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bfa3f-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bfa3f-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bfa3f-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="bfa3f-128">Requirements</span></span>  
 <span data-ttu-id="bfa3f-129">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bfa3f-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfa3f-130">**Intestazione:** IValidator. idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="bfa3f-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="bfa3f-131">**Libreria:** inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="bfa3f-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bfa3f-132">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfa3f-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfa3f-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="bfa3f-133">See Also</span></span>  
 [<span data-ttu-id="bfa3f-134">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="bfa3f-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [<span data-ttu-id="bfa3f-135">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="bfa3f-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
