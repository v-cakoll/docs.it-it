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
ms.openlocfilehash: 497a115b980bb58a3906fda68d7ff564efe78089
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127833"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="4a493-102">Metodo ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="4a493-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="4a493-103">Convalida il file eseguibile portatile (PE) o il linguaggio MSIL (Microsoft Intermediate Language) nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="4a493-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a493-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4a493-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="4a493-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4a493-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="4a493-106">in Puntatore a un'istanza di `IVEHandler` che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="4a493-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="4a493-107">in Identificatore per l'<xref:System.AppDomain>corrente.</span><span class="sxs-lookup"><span data-stu-id="4a493-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="4a493-108">in Combinazione di valori [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) , che indica il tipo di convalida da eseguire.</span><span class="sxs-lookup"><span data-stu-id="4a493-108">[in] A combination of [ValidatorFlags](../../../../docs/framework/unmanaged-api/hosting/validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="4a493-109">in Numero massimo di errori da consentire prima di uscire dalla convalida.</span><span class="sxs-lookup"><span data-stu-id="4a493-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="4a493-110">in Inutilizzati.</span><span class="sxs-lookup"><span data-stu-id="4a493-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="4a493-111">in Nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="4a493-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="4a493-112">in Puntatore al buffer di file.</span><span class="sxs-lookup"><span data-stu-id="4a493-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="4a493-113">in Dimensione, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="4a493-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4a493-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4a493-114">Return Value</span></span>  
  
|<span data-ttu-id="4a493-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4a493-115">HRESULT</span></span>|<span data-ttu-id="4a493-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4a493-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4a493-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="4a493-117">S_OK</span></span>|<span data-ttu-id="4a493-118">`Validate` ha restituito un esito positivo.</span><span class="sxs-lookup"><span data-stu-id="4a493-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="4a493-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4a493-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4a493-120">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="4a493-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4a493-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4a493-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4a493-122">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="4a493-122">The call timed out.</span></span>|  
|<span data-ttu-id="4a493-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4a493-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4a493-124">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="4a493-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4a493-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4a493-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4a493-126">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="4a493-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4a493-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4a493-127">E_FAIL</span></span>|<span data-ttu-id="4a493-128">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="4a493-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4a493-129">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="4a493-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4a493-130">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4a493-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4a493-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4a493-131">Requirements</span></span>  
 <span data-ttu-id="4a493-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a493-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a493-133">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="4a493-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="4a493-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4a493-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a493-135">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a493-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a493-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4a493-136">See also</span></span>

- [<span data-ttu-id="4a493-137">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="4a493-137">ICLRValidator Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-interface.md)
