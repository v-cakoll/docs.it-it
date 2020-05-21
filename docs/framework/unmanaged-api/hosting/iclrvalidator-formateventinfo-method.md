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
ms.openlocfilehash: 164a8c15a501af44aabb95852400621f05bbe873
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762799"
---
# <a name="iclrvalidatorformateventinfo-method"></a><span data-ttu-id="d724a-102">Metodo ICLRValidator::FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="d724a-102">ICLRValidator::FormatEventInfo Method</span></span>
<span data-ttu-id="d724a-103">Ottiene un messaggio dettagliato sull'errore di convalida specificato.</span><span class="sxs-lookup"><span data-stu-id="d724a-103">Gets a detailed message about the specified validation error.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d724a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d724a-104">Syntax</span></span>  
  
```cpp  
HRESULT FormatEventInfo (  
    [in] HRESULT            hVECode,  
    [in] VEContext          Context,  
    [in, out] LPWSTR        msg,  
    [in] unsigned long      ulMaxLength,  
    [in] SAFEARRAY(VARIANT) psa  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d724a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d724a-105">Parameters</span></span>  
 `hVECode`  
 <span data-ttu-id="d724a-106">in Valore HRESULT passato al gestore degli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="d724a-106">[in] The HRESULT value that was passed to the validation error handler.</span></span>  
  
 `Context`  
 <span data-ttu-id="d724a-107">in `VEContext`Istanza di che contiene informazioni di contesto sugli errori di convalida.</span><span class="sxs-lookup"><span data-stu-id="d724a-107">[in] A `VEContext` instance that contains context information about the validation errors.</span></span>  
  
 `msg`  
 <span data-ttu-id="d724a-108">[in, out] Messaggio di errore descrittivo.</span><span class="sxs-lookup"><span data-stu-id="d724a-108">[in, out] The friendly error message.</span></span>  
  
 `ulMaxLength`  
 <span data-ttu-id="d724a-109">in Lunghezza massima del messaggio di errore.</span><span class="sxs-lookup"><span data-stu-id="d724a-109">[in] The maximum length of the error message.</span></span>  
  
 `psa`  
 <span data-ttu-id="d724a-110">in Matrice sicura di parametri aggiuntivi da utilizzare nel messaggio.</span><span class="sxs-lookup"><span data-stu-id="d724a-110">[in] A safe array of additional parameters to be used in the message.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d724a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d724a-111">Return Value</span></span>  
  
|<span data-ttu-id="d724a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d724a-112">HRESULT</span></span>|<span data-ttu-id="d724a-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d724a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d724a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d724a-114">S_OK</span></span>|<span data-ttu-id="d724a-115">`FormatEventInfo`la restituzione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="d724a-115">`FormatEventInfo` returned successfully.</span></span>|  
|<span data-ttu-id="d724a-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d724a-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d724a-117">Il Common Language Runtime (CLR) non è stato caricato in un processo oppure CLR si trova in uno stato in cui non è possibile eseguire codice gestito o elaborare la chiamata correttamente.</span><span class="sxs-lookup"><span data-stu-id="d724a-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d724a-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d724a-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d724a-119">Timeout della chiamata.</span><span class="sxs-lookup"><span data-stu-id="d724a-119">The call timed out.</span></span>|  
|<span data-ttu-id="d724a-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d724a-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d724a-121">Il chiamante non è il proprietario del blocco.</span><span class="sxs-lookup"><span data-stu-id="d724a-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d724a-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d724a-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d724a-123">Un evento è stato annullato mentre un thread bloccato o Fiber era in attesa su di esso.</span><span class="sxs-lookup"><span data-stu-id="d724a-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d724a-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d724a-124">E_FAIL</span></span>|<span data-ttu-id="d724a-125">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="d724a-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d724a-126">Quando un metodo restituisce E_FAIL, CLR non è più utilizzabile all'interno del processo.</span><span class="sxs-lookup"><span data-stu-id="d724a-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d724a-127">Le chiamate successive ai metodi di hosting restituiscono HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d724a-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d724a-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d724a-128">Requirements</span></span>  
 <span data-ttu-id="d724a-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d724a-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d724a-130">**Intestazione:** IValidator. idl, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="d724a-130">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="d724a-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d724a-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d724a-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d724a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d724a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d724a-133">See also</span></span>

- [<span data-ttu-id="d724a-134">Interfaccia ICLRErrorReportingManager</span><span class="sxs-lookup"><span data-stu-id="d724a-134">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="d724a-135">Interfaccia ICLRValidator</span><span class="sxs-lookup"><span data-stu-id="d724a-135">ICLRValidator Interface</span></span>](iclrvalidator-interface.md)
