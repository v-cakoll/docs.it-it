---
title: Metodo ICLRValidator::Validate
ms.date: 03/30/2017
api_name:
- ICLRValidator.Validate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator::Validate
helpviewer_keywords:
- Validate method, ICLRValidator interface [.NET Framework hosting]
- ICLRValidator::Validate method [.NET Framework hosting]
ms.assetid: 0b1b432a-d234-4002-839b-81366c3a8bdc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ccd6dbe63f02fa7e28c6aec1be815f1f1967a90a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54718728"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="83edc-102">Metodo ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="83edc-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="83edc-103">Convalida il file eseguibile portabile (PE) o Microsoft intermediate language (MSIL) nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="83edc-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83edc-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="83edc-104">Syntax</span></span>  
  
```  
HRESULT Validate (  
    [in] IVEHandler        *veh,  
    [in] unsigned long      ulAppDomainId,  
    [in] unsigned long      ulFlags,  
    [in] unsigned long      ulMaxError,  
    [in] unsigned long      token,  
    [in] LPWSTR             fileName,  
    [in, size_is(ulSize)] BYTE *pe,  
    [in] unsigned long      ulSize  
);      
```  
  
#### <a name="parameters"></a><span data-ttu-id="83edc-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="83edc-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="83edc-106">[in] Un puntatore a un `IVEHandler` istanza che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="83edc-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="83edc-107">[in] L'identificatore per l'oggetto corrente <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="83edc-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="83edc-108">[in] Una combinazione di [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valori, che indica il tipo di convalida da eseguire.</span><span class="sxs-lookup"><span data-stu-id="83edc-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="83edc-109">[in] Il numero massimo di errori consentiti prima di disattivare la convalida.</span><span class="sxs-lookup"><span data-stu-id="83edc-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="83edc-110">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="83edc-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="83edc-111">[in] Il nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="83edc-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="83edc-112">[in] Puntatore al buffer di file.</span><span class="sxs-lookup"><span data-stu-id="83edc-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="83edc-113">[in] Le dimensioni, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="83edc-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="83edc-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="83edc-114">Return Value</span></span>  
  
|<span data-ttu-id="83edc-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="83edc-115">HRESULT</span></span>|<span data-ttu-id="83edc-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="83edc-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="83edc-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="83edc-117">S_OK</span></span>|<span data-ttu-id="83edc-118">`Validate` stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="83edc-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="83edc-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="83edc-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="83edc-120">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="83edc-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="83edc-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="83edc-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="83edc-122">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="83edc-122">The call timed out.</span></span>|  
|<span data-ttu-id="83edc-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="83edc-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="83edc-124">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="83edc-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="83edc-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="83edc-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="83edc-126">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="83edc-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="83edc-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="83edc-127">E_FAIL</span></span>|<span data-ttu-id="83edc-128">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="83edc-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="83edc-129">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="83edc-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="83edc-130">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="83edc-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="83edc-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="83edc-131">Requirements</span></span>  
 <span data-ttu-id="83edc-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83edc-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83edc-133">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="83edc-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="83edc-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="83edc-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="83edc-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83edc-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83edc-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="83edc-136">See also</span></span>
- [<span data-ttu-id="83edc-137">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="83edc-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
