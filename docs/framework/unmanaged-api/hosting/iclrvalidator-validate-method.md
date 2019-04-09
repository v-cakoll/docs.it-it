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
ms.openlocfilehash: 559c265c70c199e64782ba185d4925d293d6a778
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158691"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="6f463-102">Metodo ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="6f463-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="6f463-103">Convalida il file eseguibile portabile (PE) o Microsoft intermediate language (MSIL) nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="6f463-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f463-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f463-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="6f463-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f463-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="6f463-106">[in] Un puntatore a un `IVEHandler` istanza che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="6f463-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="6f463-107">[in] L'identificatore per l'oggetto corrente <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="6f463-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="6f463-108">[in] Una combinazione di [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) valori, che indica il tipo di convalida da eseguire.</span><span class="sxs-lookup"><span data-stu-id="6f463-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="6f463-109">[in] Il numero massimo di errori consentiti prima di disattivare la convalida.</span><span class="sxs-lookup"><span data-stu-id="6f463-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="6f463-110">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="6f463-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="6f463-111">[in] Il nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="6f463-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="6f463-112">[in] Puntatore al buffer di file.</span><span class="sxs-lookup"><span data-stu-id="6f463-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="6f463-113">[in] Le dimensioni, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="6f463-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f463-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6f463-114">Return Value</span></span>  
  
|<span data-ttu-id="6f463-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6f463-115">HRESULT</span></span>|<span data-ttu-id="6f463-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f463-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6f463-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f463-117">S_OK</span></span>|`Validate` <span data-ttu-id="6f463-118">stato restituito correttamente.</span><span class="sxs-lookup"><span data-stu-id="6f463-118">returned successfully.</span></span>|  
|<span data-ttu-id="6f463-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6f463-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6f463-120">Common language runtime (CLR) non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="6f463-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6f463-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6f463-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6f463-122">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6f463-122">The call timed out.</span></span>|  
|<span data-ttu-id="6f463-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6f463-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6f463-124">Il chiamante non possiede il blocco.</span><span class="sxs-lookup"><span data-stu-id="6f463-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6f463-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6f463-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6f463-126">Un evento è stato annullato durante un thread bloccato o fiber è rimasta in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="6f463-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6f463-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6f463-127">E_FAIL</span></span>|<span data-ttu-id="6f463-128">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="6f463-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6f463-129">Quando un metodo di E_FAIL viene restituito, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="6f463-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6f463-130">Le chiamate successive ai metodi di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6f463-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6f463-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f463-131">Requirements</span></span>  
 <span data-ttu-id="6f463-132">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f463-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f463-133">**Intestazione:** IValidator. idl, IValidator. H</span><span class="sxs-lookup"><span data-stu-id="6f463-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="6f463-134">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="6f463-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="6f463-135">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="6f463-135">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6f463-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f463-136">See also</span></span>

- [<span data-ttu-id="6f463-137">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="6f463-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
