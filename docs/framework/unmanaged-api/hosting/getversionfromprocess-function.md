---
title: Funzione GetVersionFromProcess
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetVersionFromProcess
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetVersionFromProcess
helpviewer_keywords:
- GetVersionFromProcess function [.NET Framework hosting]
ms.assetid: a9f7f824-64a1-408d-8607-91c7f19d21fe
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: db5054ab9b71eb93005fc0315acba82d807487ec
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="4981e-102">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="4981e-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="4981e-103">Ottiene il numero di versione di common language runtime (CLR) che è associato l'handle del processo specificato.</span><span class="sxs-lookup"><span data-stu-id="4981e-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="4981e-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4981e-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4981e-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4981e-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4981e-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="4981e-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="4981e-107">[in] Un handle a un processo.</span><span class="sxs-lookup"><span data-stu-id="4981e-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="4981e-108">[out] Un buffer che contiene la stringa del numero di versione al completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="4981e-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="4981e-109">[in] La lunghezza del buffer della versione.</span><span class="sxs-lookup"><span data-stu-id="4981e-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="4981e-110">[out] Puntatore alla lunghezza della stringa di numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="4981e-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4981e-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="4981e-111">Return Value</span></span>  
 <span data-ttu-id="4981e-112">Questo metodo restituisce codici di errore standard del modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="4981e-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="4981e-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="4981e-113">Return code</span></span>|<span data-ttu-id="4981e-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="4981e-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="4981e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="4981e-115">S_OK</span></span>|<span data-ttu-id="4981e-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="4981e-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="4981e-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="4981e-117">E_INVALIDARG</span></span>|<span data-ttu-id="4981e-118">`pVersion`è null e `cchBuffer` non è null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="4981e-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="4981e-119">oppure</span><span class="sxs-lookup"><span data-stu-id="4981e-119">-or-</span></span><br /><br /> <span data-ttu-id="4981e-120">`hProcess`non è un handle a un processo valido.</span><span class="sxs-lookup"><span data-stu-id="4981e-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="4981e-121">oppure</span><span class="sxs-lookup"><span data-stu-id="4981e-121">-or-</span></span><br /><br /> <span data-ttu-id="4981e-122">CLR non è caricato.</span><span class="sxs-lookup"><span data-stu-id="4981e-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="4981e-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="4981e-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="4981e-124">`cchBuffer`è null o inferiore alla lunghezza della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="4981e-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="4981e-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="4981e-125">E_NOTIMPL</span></span>|<span data-ttu-id="4981e-126">Questo metodo non è disponibile nel sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Windows Millennium Edition di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4981e-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4981e-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4981e-127">Requirements</span></span>  
 <span data-ttu-id="4981e-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4981e-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4981e-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="4981e-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4981e-130">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4981e-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4981e-131">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4981e-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4981e-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4981e-132">See Also</span></span>  
 [<span data-ttu-id="4981e-133">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="4981e-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="4981e-134">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="4981e-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [<span data-ttu-id="4981e-135">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="4981e-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
