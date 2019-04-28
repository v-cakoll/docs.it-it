---
title: Funzione GetRequestedRuntimeInfo
ms.date: 03/30/2017
api_name:
- GetRequestedRuntimeInfo
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetRequestedRuntimeInfo
helpviewer_keywords:
- GetRequestedRuntimeInfo function [.NET Framework hosting]
ms.assetid: 0dfd7cdc-c116-4e25-b56a-ac7b0378c942
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1290aa864a3f65e549bc26173dcd23648b8dee90
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61627984"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="96d6b-102">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="96d6b-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="96d6b-103">Ottiene informazioni di versione e la directory di common language runtime (CLR) richiesto da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="96d6b-104">Questa funzione è stata deprecata nel [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="96d6b-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="96d6b-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="96d6b-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeInfo (  
    [in]  LPCWSTR  pExe,   
    [in]  LPCWSTR  pwszVersion,   
    [in]  LPCWSTR  pConfigurationFile,   
    [in]  DWORD    startupFlags,   
    [in]  DWORD    runtimeInfoFlags,   
    [out] LPWSTR   pDirectory,   
    [in]  DWORD    dwDirectory,   
    [out] DWORD   *dwDirectoryLength,   
    [out] LPWSTR   pVersion,   
    [in]  DWORD    cchBuffer,   
    [out] DWORD   *dwlength  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="96d6b-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="96d6b-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="96d6b-107">[in] Il nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="96d6b-108">[in] Stringa che specifica il numero di versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="96d6b-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="96d6b-109">[in] Il nome del file di configurazione associato `pExe`.</span><span class="sxs-lookup"><span data-stu-id="96d6b-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="96d6b-110">[in] Uno o più i [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="96d6b-111">[in] Uno o più i [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="96d6b-112">[out] Un buffer che contiene il percorso della directory per il runtime di una volta completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="96d6b-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="96d6b-113">[in] La lunghezza del buffer della directory.</span><span class="sxs-lookup"><span data-stu-id="96d6b-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="96d6b-114">[out] Puntatore alla lunghezza della stringa di percorso di directory.</span><span class="sxs-lookup"><span data-stu-id="96d6b-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="96d6b-115">[out] Un buffer che contiene il numero di versione del runtime di una volta completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="96d6b-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="96d6b-116">[in] La lunghezza del buffer di stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="96d6b-117">[out] Puntatore alla lunghezza della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="96d6b-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="96d6b-118">Return Value</span></span>  
 <span data-ttu-id="96d6b-119">Questo metodo restituisce codici di errore standard modello COM (Component Object), come definito nel file Winerror. H, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="96d6b-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="96d6b-120">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="96d6b-120">Return code</span></span>|<span data-ttu-id="96d6b-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="96d6b-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="96d6b-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="96d6b-122">S_OK</span></span>|<span data-ttu-id="96d6b-123">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="96d6b-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="96d6b-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="96d6b-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="96d6b-125">Il buffer di directory non è sufficiente per archiviare il percorso della directory.</span><span class="sxs-lookup"><span data-stu-id="96d6b-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="96d6b-126">-oppure-</span><span class="sxs-lookup"><span data-stu-id="96d6b-126">- or -</span></span><br /><br /> <span data-ttu-id="96d6b-127">Il buffer di versione non è sufficiente per archiviare la stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="96d6b-128">Note</span><span class="sxs-lookup"><span data-stu-id="96d6b-128">Remarks</span></span>  
 <span data-ttu-id="96d6b-129">Il `GetRequestedRuntimeInfo` metodo restituisce le informazioni di runtime relative alla versione caricata nel processo, che non è necessariamente la versione più recente installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="96d6b-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="96d6b-130">In .NET Framework versione 2.0, è possibile ottenere informazioni sull'ultima versione installata tramite il `GetRequestedRuntimeInfo` metodo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="96d6b-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="96d6b-131">Specificare il `pExe`, `pwszVersion`, e `pConfigurationFile` parametri come valori null.</span><span class="sxs-lookup"><span data-stu-id="96d6b-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="96d6b-132">Specificare il flag RUNTIME_INFO_UPGRADE_VERSION nel `RUNTIME_INFO_FLAGS` enumerazioni per il `runtimeInfoFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="96d6b-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="96d6b-133">Il `GetRequestedRuntimeInfo` metodo non restituisce la versione più recente di Common Language Runtime nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="96d6b-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="96d6b-134">Esiste un file di configurazione che specifica il caricamento di una particolare versione CLR.</span><span class="sxs-lookup"><span data-stu-id="96d6b-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="96d6b-135">Si noti che .NET Framework utilizzerà il file di configurazione anche se si specifica null per il `pConfigurationFile` parametro.</span><span class="sxs-lookup"><span data-stu-id="96d6b-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="96d6b-136">Il [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) metodo è stato chiamato specificando una versione precedente di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="96d6b-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="96d6b-137">Un'applicazione che è stata compilata per una versione precedente di Common Language Runtime è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="96d6b-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="96d6b-138">Per il `runtimeInfoFlags` parametro, è possibile specificare solo una delle costanti dell'architettura di `RUNTIME_INFO_FLAGS` enumerazione per volta:</span><span class="sxs-lookup"><span data-stu-id="96d6b-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="96d6b-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="96d6b-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="96d6b-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="96d6b-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="96d6b-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="96d6b-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="96d6b-142">Requisiti</span><span class="sxs-lookup"><span data-stu-id="96d6b-142">Requirements</span></span>  
 <span data-ttu-id="96d6b-143">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="96d6b-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="96d6b-144">**Intestazione:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="96d6b-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="96d6b-145">**Libreria:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="96d6b-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="96d6b-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="96d6b-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96d6b-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96d6b-147">See also</span></span>

- [<span data-ttu-id="96d6b-148">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="96d6b-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="96d6b-149">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="96d6b-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="96d6b-150">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="96d6b-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
