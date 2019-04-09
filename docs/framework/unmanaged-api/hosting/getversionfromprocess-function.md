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
ms.openlocfilehash: 452104939acf5de7bb151cba00d65fb6631c98d5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59124085"
---
# <a name="getversionfromprocess-function"></a><span data-ttu-id="d898c-102">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="d898c-102">GetVersionFromProcess Function</span></span>
<span data-ttu-id="d898c-103">Ottiene il numero di versione di common language runtime (CLR) che viene associato all'handle del processo specificato.</span><span class="sxs-lookup"><span data-stu-id="d898c-103">Gets the version number of the common language runtime (CLR) that is associated with the specified process handle.</span></span>  
  
 <span data-ttu-id="d898c-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d898c-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d898c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d898c-105">Syntax</span></span>  
  
```  
HRESULT GetVersionFromProcess (  
    [in]  HANDLE  hProcess,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *dwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d898c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="d898c-106">Parameters</span></span>  
 `hProcess`  
 <span data-ttu-id="d898c-107">[in] Handle per un processo.</span><span class="sxs-lookup"><span data-stu-id="d898c-107">[in] A handle to a process.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="d898c-108">[out] Un buffer che contiene la stringa del numero di versione al completamento del metodo.</span><span class="sxs-lookup"><span data-stu-id="d898c-108">[out] A buffer that contains the version number string upon successful completion of the method.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="d898c-109">[in] La lunghezza del buffer della versione.</span><span class="sxs-lookup"><span data-stu-id="d898c-109">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="d898c-110">[out] Puntatore alla lunghezza della stringa di numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="d898c-110">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d898c-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="d898c-111">Return Value</span></span>  
 <span data-ttu-id="d898c-112">Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="d898c-112">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="d898c-113">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="d898c-113">Return code</span></span>|<span data-ttu-id="d898c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="d898c-114">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="d898c-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="d898c-115">S_OK</span></span>|<span data-ttu-id="d898c-116">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="d898c-116">The method completed successfully.</span></span>|  
|<span data-ttu-id="d898c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="d898c-117">E_INVALIDARG</span></span>|`pVersion` <span data-ttu-id="d898c-118">è null e `cchBuffer` non è null, o viceversa.</span><span class="sxs-lookup"><span data-stu-id="d898c-118">is null and `cchBuffer` is not null, or vice versa.</span></span><br /><br /> <span data-ttu-id="d898c-119">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d898c-119">-or-</span></span><br /><br /> `hProcess` <span data-ttu-id="d898c-120">non è un handle valido a un processo.</span><span class="sxs-lookup"><span data-stu-id="d898c-120">is not a valid handle to a process.</span></span><br /><br /> <span data-ttu-id="d898c-121">-oppure-</span><span class="sxs-lookup"><span data-stu-id="d898c-121">-or-</span></span><br /><br /> <span data-ttu-id="d898c-122">CLR non è caricato.</span><span class="sxs-lookup"><span data-stu-id="d898c-122">The CLR is not loaded.</span></span>|  
|<span data-ttu-id="d898c-123">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="d898c-123">ERROR_INSUFFICIENT_BUFFER</span></span>|`cchBuffer` <span data-ttu-id="d898c-124">è null o minore della lunghezza della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="d898c-124">is null or less than the length of the version string.</span></span>|  
|<span data-ttu-id="d898c-125">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="d898c-125">E_NOTIMPL</span></span>|<span data-ttu-id="d898c-126">Questo metodo non è disponibile nel sistema operativo Microsoft Windows 95, Microsoft Windows 98 o Microsoft Windows Millennium Edition.</span><span class="sxs-lookup"><span data-stu-id="d898c-126">This method is not available on the Microsoft Windows 95, Microsoft Windows 98, or Microsoft Windows Millennium Edition operating system.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d898c-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d898c-127">Requirements</span></span>  
 <span data-ttu-id="d898c-128">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d898c-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d898c-129">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d898c-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d898c-130">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d898c-130">**Library:** MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d898c-131">Versioni di .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d898c-131">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d898c-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d898c-132">See also</span></span>

- [<span data-ttu-id="d898c-133">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="d898c-133">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="d898c-134">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="d898c-134">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="d898c-135">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="d898c-135">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
