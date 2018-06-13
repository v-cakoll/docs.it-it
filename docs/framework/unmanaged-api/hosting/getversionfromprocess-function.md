---
title: Funzione GetVersionFromProcess
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0b57d04a8a49371872c679a331b5ae9c45dce797
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433073"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="f595a-102">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="f595a-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="f595a-103">Ottiene il numero di versione di common language runtime (CLR) che è associato l'handle del processo specificato.</span><span class="sxs-lookup"><span data-stu-id="f595a-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="f595a-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f595a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f595a-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f595a-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f595a-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="f595a-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="f595a-107">[in] Un handle a un processo.</span><span class="sxs-lookup"><span data-stu-id="f595a-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="f595a-108">[out] Un buffer che contiene la stringa del numero di versione al completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="f595a-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="f595a-109">[in] La lunghezza del buffer della versione.</span><span class="sxs-lookup"><span data-stu-id="f595a-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="f595a-110">[out] Puntatore alla lunghezza della stringa di numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="f595a-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f595a-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f595a-111">Return Value</span></span>  
 <span data-ttu-id="f595a-112">Questo metodo restituisce codici di errore standard del modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="f595a-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="f595a-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="f595a-113">Return code</span></span>|<span data-ttu-id="f595a-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f595a-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="f595a-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="f595a-115">S_OK</span></span>|<span data-ttu-id="f595a-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="f595a-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="f595a-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="f595a-117">E_INVALIDARG</span></span>|<span data-ttu-id="f595a-118">`pVersion` è null e `cchBuffer` non è null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="f595a-118">`pVersion` is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="f595a-119">oppure</span><span class="sxs-lookup"><span data-stu-id="f595a-119">-or-</span></span><br /><br /> <span data-ttu-id="f595a-120">`hProcess` non è un handle valido a un processo.</span><span class="sxs-lookup"><span data-stu-id="f595a-120">`hProcess` is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="f595a-121">oppure</span><span class="sxs-lookup"><span data-stu-id="f595a-121">-or-</span></span><br /><br /> <span data-ttu-id="f595a-122">CLR non è caricato.</span><span class="sxs-lookup"><span data-stu-id="f595a-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="f595a-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="f595a-123">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="f595a-124">`cchBuffer` è null o minore della lunghezza della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="f595a-124">`cchBuffer` is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="f595a-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="f595a-125">E_NOTIMPL</span></span>|<span data-ttu-id="f595a-126">Questo metodo non è disponibile nel sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Windows Millennium Edition di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f595a-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f595a-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f595a-127">Requirements</span></span>  
 <span data-ttu-id="f595a-128">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f595a-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f595a-129">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="f595a-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f595a-130">**Libreria:** Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f595a-130">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f595a-131">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f595a-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f595a-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f595a-132">See Also</span></span>  
 [<span data-ttu-id="f595a-133">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="f595a-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)  
 [<span data-ttu-id="f595a-134">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="f595a-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)  
 [<span data-ttu-id="f595a-135">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="f595a-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
