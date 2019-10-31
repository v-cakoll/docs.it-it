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
ms.openlocfilehash: cd1d9e768698115bee22e35699b044e0c3526d2d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136314"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="ae404-102">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="ae404-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="ae404-103">Ottiene le informazioni sulla versione e sulla directory relative alla Common Language Runtime (CLR) richiesta da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae404-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="ae404-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="ae404-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae404-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae404-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="ae404-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae404-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="ae404-107">in Nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="ae404-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="ae404-108">in Stringa che specifica il numero di versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="ae404-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="ae404-109">in Nome del file di configurazione associato a `pExe`.</span><span class="sxs-lookup"><span data-stu-id="ae404-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="ae404-110">in Uno o più valori di enumerazione [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ae404-110">[in] One or more of the [STARTUP_FLAGS](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="ae404-111">in Uno o più valori di enumerazione [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="ae404-111">[in] One or more of the [RUNTIME_INFO_FLAGS](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="ae404-112">out Buffer che contiene il percorso di directory del runtime dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="ae404-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="ae404-113">in Lunghezza del buffer di directory.</span><span class="sxs-lookup"><span data-stu-id="ae404-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="ae404-114">out Puntatore alla lunghezza della stringa del percorso di directory.</span><span class="sxs-lookup"><span data-stu-id="ae404-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="ae404-115">out Buffer che contiene il numero di versione del runtime dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="ae404-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="ae404-116">in Lunghezza del buffer della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="ae404-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="ae404-117">out Puntatore alla lunghezza della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="ae404-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae404-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ae404-118">Return Value</span></span>  
 <span data-ttu-id="ae404-119">Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ae404-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="ae404-120">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="ae404-120">Return code</span></span>|<span data-ttu-id="ae404-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae404-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="ae404-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="ae404-122">S_OK</span></span>|<span data-ttu-id="ae404-123">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="ae404-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="ae404-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="ae404-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="ae404-125">Il buffer di directory non è abbastanza grande per archiviare il percorso della directory.</span><span class="sxs-lookup"><span data-stu-id="ae404-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="ae404-126">-oppure-</span><span class="sxs-lookup"><span data-stu-id="ae404-126">- or -</span></span><br /><br /> <span data-ttu-id="ae404-127">Il buffer della versione non è abbastanza grande per archiviare la stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="ae404-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ae404-128">Note</span><span class="sxs-lookup"><span data-stu-id="ae404-128">Remarks</span></span>  
 <span data-ttu-id="ae404-129">Il metodo `GetRequestedRuntimeInfo` restituisce informazioni in fase di esecuzione sulla versione caricata nel processo, che non è necessariamente la versione più recente installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="ae404-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="ae404-130">Nel .NET Framework versione 2,0, è possibile ottenere informazioni sull'ultima versione installata usando il metodo `GetRequestedRuntimeInfo` come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ae404-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="ae404-131">Specificare i parametri `pExe`, `pwszVersion`e `pConfigurationFile` come null.</span><span class="sxs-lookup"><span data-stu-id="ae404-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="ae404-132">Specificare il flag RUNTIME_INFO_UPGRADE_VERSION nelle enumerazioni `RUNTIME_INFO_FLAGS` per il parametro `runtimeInfoFlags`.</span><span class="sxs-lookup"><span data-stu-id="ae404-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="ae404-133">Il metodo `GetRequestedRuntimeInfo` non restituisce la versione più recente di CLR nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="ae404-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="ae404-134">Un file di configurazione dell'applicazione che specifica il caricamento di una determinata versione di CLR esiste.</span><span class="sxs-lookup"><span data-stu-id="ae404-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="ae404-135">Si noti che il .NET Framework utilizzerà il file di configurazione anche se si specifica null per il parametro `pConfigurationFile`.</span><span class="sxs-lookup"><span data-stu-id="ae404-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="ae404-136">Il metodo [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) è stato chiamato specificando una versione precedente di CLR.</span><span class="sxs-lookup"><span data-stu-id="ae404-136">The [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="ae404-137">Un'applicazione compilata per una versione CLR precedente è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="ae404-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="ae404-138">Per il parametro `runtimeInfoFlags`, è possibile specificare solo una delle costanti di architettura dell'enumerazione `RUNTIME_INFO_FLAGS` alla volta:</span><span class="sxs-lookup"><span data-stu-id="ae404-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="ae404-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="ae404-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="ae404-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="ae404-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="ae404-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="ae404-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae404-142">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae404-142">Requirements</span></span>  
 <span data-ttu-id="ae404-143">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae404-143">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae404-144">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ae404-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ae404-145">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ae404-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae404-146">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae404-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae404-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae404-147">See also</span></span>

- [<span data-ttu-id="ae404-148">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="ae404-148">GetRequestedRuntimeVersion Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getrequestedruntimeversion-function.md)
- [<span data-ttu-id="ae404-149">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="ae404-149">GetVersionFromProcess Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md)
- [<span data-ttu-id="ae404-150">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="ae404-150">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
