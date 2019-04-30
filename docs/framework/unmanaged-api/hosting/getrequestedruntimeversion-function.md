---
title: Funzione GetRequestedRuntimeVersion
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeVersion
helpviewer_keywords:
- GetRequestedRuntimeVersion function [.NET Framework hosting]
ms.assetid: 82f596a4-483d-4509-b0c5-a84c53c3da1b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ee737f4c6d34e77996f5ba08ce4d84132a99238
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61985660"
---
# <a name="getrequestedruntimeversion-function"></a><span data-ttu-id="6bbdb-102">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="6bbdb-102">GetRequestedRuntimeVersion Function</span></span>
<span data-ttu-id="6bbdb-103">Ottiene il numero di versione di common language runtime (CLR) richiesto dall'applicazione specificata.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-103">Gets the version number of the common language runtime (CLR) requested by the specified application.</span></span> <span data-ttu-id="6bbdb-104">Se non viene installata la versione, ottiene la versione più recente installata prima della versione richiesta.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-104">If that version is not installed, gets the most recent version that is installed before the requested version.</span></span>  
  
 <span data-ttu-id="6bbdb-105">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6bbdb-105">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6bbdb-106">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6bbdb-106">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersion (  
    [in]  LPWSTR  pExe,   
    [out] LPWSTR  pVersion,   
    [in]  DWORD   cchBuffer,   
    [out] DWORD  *pdwLength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6bbdb-107">Parametri</span><span class="sxs-lookup"><span data-stu-id="6bbdb-107">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="6bbdb-108">[in] Il nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-108">[in] The name of the application.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="6bbdb-109">[out] Un buffer che contiene la stringa del numero di versione al completamento.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-109">[out] A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="6bbdb-110">[in] La lunghezza del buffer della versione.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-110">[in] The length of the version buffer.</span></span>  
  
 `pdwLength`  
 <span data-ttu-id="6bbdb-111">[out] Puntatore alla lunghezza della stringa di numeri di versione.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-111">[out] A pointer to the length of the version number string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6bbdb-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6bbdb-112">Return Value</span></span>  
 <span data-ttu-id="6bbdb-113">Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-113">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="6bbdb-114">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="6bbdb-114">Return code</span></span>|<span data-ttu-id="6bbdb-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6bbdb-115">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6bbdb-116">S_OK</span><span class="sxs-lookup"><span data-stu-id="6bbdb-116">S_OK</span></span>|<span data-ttu-id="6bbdb-117">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-117">The method completed successfully.</span></span>|  
|<span data-ttu-id="6bbdb-118">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="6bbdb-118">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="6bbdb-119">Il buffer di versione non è sufficiente per archiviare la stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-119">The version buffer is not large enough to store the version string.</span></span>|  
|<span data-ttu-id="6bbdb-120">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6bbdb-120">E_POINTER</span></span>|<span data-ttu-id="6bbdb-121">`pdwLength` è null.</span><span class="sxs-lookup"><span data-stu-id="6bbdb-121">`pdwLength` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6bbdb-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6bbdb-122">Requirements</span></span>  
 <span data-ttu-id="6bbdb-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6bbdb-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6bbdb-124">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="6bbdb-124">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6bbdb-125">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6bbdb-125">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6bbdb-126">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6bbdb-126">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6bbdb-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6bbdb-127">See also</span></span>

- [<span data-ttu-id="6bbdb-128">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="6bbdb-128">GetRequestedRuntimeInfo Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeinfo-function.md)
- [<span data-ttu-id="6bbdb-129">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="6bbdb-129">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="6bbdb-130">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="6bbdb-130">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
