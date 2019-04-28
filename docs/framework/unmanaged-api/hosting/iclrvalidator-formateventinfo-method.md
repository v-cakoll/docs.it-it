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
ms.openlocfilehash: 9117a82dff48dcda8d96f0feb7b8c4a001fa17f1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763321"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="d3c59-102">Metodo ICLRValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="d3c59-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="d3c59-103">Ottiene un messaggio dettagliato sull'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="d3c59-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3c59-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3c59-104">Syntax</span></span>  
  
```  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3c59-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3c59-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="d3c59-106">[in] Il valore HRESULT passato al gestore di errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="d3c59-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="d3c59-107">[in] Oggetto `VEContext` istanza che contiene informazioni contestuali relative agli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="d3c59-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="d3c59-108">[in, out] Il messaggio di errore descrittivo.</span><span class="sxs-lookup"><span data-stu-id="d3c59-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="d3c59-109">[in] La lunghezza massima del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d3c59-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="d3c59-110">[in] Una matrice protetta di parametri aggiuntivi da utilizzare nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="d3c59-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d3c59-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d3c59-111">Return Value</span></span>  
  
|<span data-ttu-id="d3c59-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d3c59-112">HRESULT</span></span>|<span data-ttu-id="d3c59-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d3c59-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d3c59-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d3c59-114">S_OK</span></span>|<span data-ttu-id="d3c59-115">`FormatEventInfo` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="d3c59-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="d3c59-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d3c59-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d3c59-117">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="d3c59-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d3c59-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d3c59-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d3c59-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d3c59-119">The call timed out.</span></span>|  
|<span data-ttu-id="d3c59-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d3c59-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d3c59-121">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="d3c59-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d3c59-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d3c59-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d3c59-123">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d3c59-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d3c59-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d3c59-124">E_FAIL</span></span>|<span data-ttu-id="d3c59-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d3c59-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d3c59-126">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d3c59-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d3c59-127">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d3c59-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3c59-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3c59-128">Requirements</span></span>  
 <span data-ttu-id="d3c59-129">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3c59-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3c59-130">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="d3c59-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d3c59-131">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="d3c59-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3c59-132">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3c59-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3c59-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d3c59-133">See also</span></span>

- [<span data-ttu-id="d3c59-134">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="d3c59-134">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="d3c59-135">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="d3c59-135">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
