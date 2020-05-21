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
ms.openlocfilehash: 18492f3e95947a3a11da9d5d303651c04d764a8f
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762630"
---
# <a name="iclrvalidatorvalidate-method"></a><span data-ttu-id="282a7-102">Metodo ICLRValidator::Validate</span><span class="sxs-lookup"><span data-stu-id="282a7-102">ICLRValidator::Validate Method</span></span>
<span data-ttu-id="282a7-103">Convalida il file eseguibile portatile (PE) o il linguaggio MSIL (Microsoft Intermediate Language) nel file specificato.</span><span class="sxs-lookup"><span data-stu-id="282a7-103">Validates the portable executable (PE) or Microsoft intermediate language (MSIL) in the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="282a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="282a7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="282a7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="282a7-105">Parameters</span></span>  
 `veh`  
 <span data-ttu-id="282a7-106">in Puntatore a un' `IVEHandler` istanza di che gestisce gli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="282a7-106">[in] A pointer to an `IVEHandler` instance that handles validation errors.</span></span>  
  
 `ulAppDomainId`  
 <span data-ttu-id="282a7-107">in Identificatore per l'oggetto corrente <xref:System.AppDomain> .</span><span class="sxs-lookup"><span data-stu-id="282a7-107">[in] The identifier for the current <xref:System.AppDomain>.</span></span>  
  
 `ulFlags`  
 <span data-ttu-id="282a7-108">in Combinazione di valori [ValidatorFlags](validatorflags-enumeration.md) , che indica il tipo di convalida da eseguire.</span><span class="sxs-lookup"><span data-stu-id="282a7-108">[in] A combination of [ValidatorFlags](validatorflags-enumeration.md) values, indicating the kind of validation that should be performed.</span></span>  
  
 `ulMaxError`  
 <span data-ttu-id="282a7-109">in Numero massimo di errori da consentire prima di uscire dalla convalida.</span><span class="sxs-lookup"><span data-stu-id="282a7-109">[in] The maximum number of errors to allow before exiting the validation.</span></span>  
  
 `token`  
 <span data-ttu-id="282a7-110">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="282a7-110">[in] Unused.</span></span>  
  
 `fileName`  
 <span data-ttu-id="282a7-111">in Nome del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="282a7-111">[in] The name of the file to be validated.</span></span>  
  
 `pe`  
 <span data-ttu-id="282a7-112">in Puntatore al buffer di file.</span><span class="sxs-lookup"><span data-stu-id="282a7-112">[in] A pointer to the file buffer.</span></span>  
  
 `ulSize`  
 <span data-ttu-id="282a7-113">in Dimensione, in byte, del file da convalidare.</span><span class="sxs-lookup"><span data-stu-id="282a7-113">[in] The size, in bytes, of the file to be validated.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="282a7-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="282a7-114">Return Value</span></span>  
  
|<span data-ttu-id="282a7-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="282a7-115">HRESULT</span></span>|<span data-ttu-id="282a7-116">Descrizione</span><span class="sxs-lookup"><span data-stu-id="282a7-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="282a7-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="282a7-117">S_OK</span></span>|<span data-ttu-id="282a7-118">`Validate`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="282a7-118">`Validate` returned successfully.</span></span>|  
|<span data-ttu-id="282a7-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="282a7-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="282a7-120">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="282a7-120">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="282a7-121">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="282a7-121">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="282a7-122">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="282a7-122">The call timed out.</span></span>|  
|<span data-ttu-id="282a7-123">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="282a7-123">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="282a7-124">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="282a7-124">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="282a7-125">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="282a7-125">HOST_E_ABANDONED</span></span>|<span data-ttu-id="282a7-126">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="282a7-126">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="282a7-127">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="282a7-127">E_FAIL</span></span>|<span data-ttu-id="282a7-128">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="282a7-128">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="282a7-129">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="282a7-129">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="282a7-130">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="282a7-130">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="282a7-131">Requisiti</span><span class="sxs-lookup"><span data-stu-id="282a7-131">Requirements</span></span>  
 <span data-ttu-id="282a7-132">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="282a7-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="282a7-133">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="282a7-133">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="282a7-134">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="282a7-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="282a7-135">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="282a7-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="282a7-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="282a7-136">See also</span></span>

- [<span data-ttu-id="282a7-137">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="282a7-137">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
