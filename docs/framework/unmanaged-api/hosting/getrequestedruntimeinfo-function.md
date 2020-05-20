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
ms.openlocfilehash: 0efda458d51677fcd16140cd0f0a835b76c20173
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617178"
---
# <a name="getrequestedruntimeinfo-function"></a><span data-ttu-id="85bf8-102">Funzione GetRequestedRuntimeInfo</span><span class="sxs-lookup"><span data-stu-id="85bf8-102">GetRequestedRuntimeInfo Function</span></span>
<span data-ttu-id="85bf8-103">Ottiene le informazioni sulla versione e sulla directory relative alla Common Language Runtime (CLR) richiesta da un'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85bf8-103">Gets version and directory information about the common language runtime (CLR) requested by an application.</span></span>  
  
 <span data-ttu-id="85bf8-104">Questa funzione è stata deprecata nel .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="85bf8-104">This function has been deprecated in the .NET Framework 4.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85bf8-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="85bf8-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="85bf8-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="85bf8-106">Parameters</span></span>  
 `pExe`  
 <span data-ttu-id="85bf8-107">in Nome dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="85bf8-107">[in] The name of the application.</span></span>  
  
 `pwszVersion`  
 <span data-ttu-id="85bf8-108">in Stringa che specifica il numero di versione del runtime.</span><span class="sxs-lookup"><span data-stu-id="85bf8-108">[in] A string specifying the version number of the runtime.</span></span>  
  
 `pConfigurationFile`  
 <span data-ttu-id="85bf8-109">in Nome del file di configurazione associato a `pExe` .</span><span class="sxs-lookup"><span data-stu-id="85bf8-109">[in] The name of the configuration file that is associated with `pExe`.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="85bf8-110">in Uno o più valori dell'enumerazione [STARTUP_FLAGS](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="85bf8-110">[in] One or more of the [STARTUP_FLAGS](startup-flags-enumeration.md) enumeration values.</span></span>  
  
 `runtimeInfoFlags`  
 <span data-ttu-id="85bf8-111">in Uno o più valori dell'enumerazione [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="85bf8-111">[in] One or more of the [RUNTIME_INFO_FLAGS](runtime-info-flags-enumeration.md) enumeration values.</span></span>  
  
 `pDirectory`  
 <span data-ttu-id="85bf8-112">out Buffer che contiene il percorso di directory del runtime dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="85bf8-112">[out] A buffer that contains the directory path to the runtime upon successful completion.</span></span>  
  
 `dwDirectory`  
 <span data-ttu-id="85bf8-113">in Lunghezza del buffer di directory.</span><span class="sxs-lookup"><span data-stu-id="85bf8-113">[in] The length of the directory buffer.</span></span>  
  
 `dwDirectoryLength`  
 <span data-ttu-id="85bf8-114">out Puntatore alla lunghezza della stringa del percorso di directory.</span><span class="sxs-lookup"><span data-stu-id="85bf8-114">[out] A pointer to the length of the directory path string.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="85bf8-115">out Buffer che contiene il numero di versione del runtime dopo il completamento.</span><span class="sxs-lookup"><span data-stu-id="85bf8-115">[out] A buffer that contains the version number of the runtime upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="85bf8-116">in Lunghezza del buffer della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="85bf8-116">[in] The length of the version string buffer.</span></span>  
  
 `dwlength`  
 <span data-ttu-id="85bf8-117">out Puntatore alla lunghezza della stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="85bf8-117">[out] A pointer to the length of the version string.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="85bf8-118">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="85bf8-118">Return Value</span></span>  
 <span data-ttu-id="85bf8-119">Questo metodo restituisce i codici di errore standard Component Object Model (COM), come definito in WinError. h, oltre ai valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="85bf8-119">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="85bf8-120">Codice restituito</span><span class="sxs-lookup"><span data-stu-id="85bf8-120">Return code</span></span>|<span data-ttu-id="85bf8-121">Description</span><span class="sxs-lookup"><span data-stu-id="85bf8-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="85bf8-122">S_OK</span><span class="sxs-lookup"><span data-stu-id="85bf8-122">S_OK</span></span>|<span data-ttu-id="85bf8-123">Metodo completato correttamente.</span><span class="sxs-lookup"><span data-stu-id="85bf8-123">The method completed successfully.</span></span>|  
|<span data-ttu-id="85bf8-124">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="85bf8-124">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="85bf8-125">Il buffer di directory non è abbastanza grande per archiviare il percorso della directory.</span><span class="sxs-lookup"><span data-stu-id="85bf8-125">The directory buffer is not large enough to store the directory path.</span></span><br /><br /> <span data-ttu-id="85bf8-126">- oppure -</span><span class="sxs-lookup"><span data-stu-id="85bf8-126">- or -</span></span><br /><br /> <span data-ttu-id="85bf8-127">Il buffer della versione non è abbastanza grande per archiviare la stringa di versione.</span><span class="sxs-lookup"><span data-stu-id="85bf8-127">The version buffer is not large enough to store the version string.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="85bf8-128">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="85bf8-128">Remarks</span></span>  
 <span data-ttu-id="85bf8-129">Il `GetRequestedRuntimeInfo` metodo restituisce informazioni in fase di esecuzione sulla versione caricata nel processo, che non è necessariamente la versione più recente installata nel computer.</span><span class="sxs-lookup"><span data-stu-id="85bf8-129">The `GetRequestedRuntimeInfo` method returns run-time information about the version loaded into the process, which is not necessarily the latest version installed on the computer.</span></span>  
  
 <span data-ttu-id="85bf8-130">Nel .NET Framework versione 2,0, è possibile ottenere informazioni sull'ultima versione installata usando il `GetRequestedRuntimeInfo` metodo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="85bf8-130">In the .NET Framework version 2.0, you can get information about the latest installed version by using the `GetRequestedRuntimeInfo` method as follows:</span></span>  
  
- <span data-ttu-id="85bf8-131">Specificare i `pExe` `pwszVersion` parametri, e `pConfigurationFile` come null.</span><span class="sxs-lookup"><span data-stu-id="85bf8-131">Specify the `pExe`, `pwszVersion`, and `pConfigurationFile` parameters as null.</span></span>  
  
- <span data-ttu-id="85bf8-132">Specificare il flag di RUNTIME_INFO_UPGRADE_VERSION nelle `RUNTIME_INFO_FLAGS` enumerazioni per il `runtimeInfoFlags` parametro.</span><span class="sxs-lookup"><span data-stu-id="85bf8-132">Specify the RUNTIME_INFO_UPGRADE_VERSION flag in the `RUNTIME_INFO_FLAGS` enumerations for the `runtimeInfoFlags` parameter.</span></span>  
  
 <span data-ttu-id="85bf8-133">Il `GetRequestedRuntimeInfo` metodo non restituisce la versione più recente di CLR nelle circostanze seguenti:</span><span class="sxs-lookup"><span data-stu-id="85bf8-133">The `GetRequestedRuntimeInfo` method does not return the latest CLR version in the following circumstances:</span></span>  
  
- <span data-ttu-id="85bf8-134">Un file di configurazione dell'applicazione che specifica il caricamento di una determinata versione di CLR esiste.</span><span class="sxs-lookup"><span data-stu-id="85bf8-134">An application configuration file that specifies loading a particular CLR version exists.</span></span> <span data-ttu-id="85bf8-135">Si noti che il .NET Framework utilizzerà il file di configurazione anche se si specifica null per il `pConfigurationFile` parametro.</span><span class="sxs-lookup"><span data-stu-id="85bf8-135">Note that the .NET Framework will use the configuration file even if you specify null for the `pConfigurationFile` parameter.</span></span>  
  
- <span data-ttu-id="85bf8-136">Il metodo [CorBindToRuntimeEx](corbindtoruntimeex-function.md) è stato chiamato specificando una versione precedente di CLR.</span><span class="sxs-lookup"><span data-stu-id="85bf8-136">The [CorBindToRuntimeEx](corbindtoruntimeex-function.md) method was called specifying an earlier CLR version.</span></span>  
  
- <span data-ttu-id="85bf8-137">Un'applicazione compilata per una versione CLR precedente è attualmente in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="85bf8-137">An application that was compiled for an earlier CLR version is currently running.</span></span>  
  
 <span data-ttu-id="85bf8-138">Per il `runtimeInfoFlags` parametro, è possibile specificare solo una delle costanti di architettura dell' `RUNTIME_INFO_FLAGS` enumerazione alla volta:</span><span class="sxs-lookup"><span data-stu-id="85bf8-138">For the `runtimeInfoFlags` parameter, you can specify only one of the architecture constants of the `RUNTIME_INFO_FLAGS` enumeration at a time:</span></span>  
  
- <span data-ttu-id="85bf8-139">RUNTIME_INFO_REQUEST_IA64</span><span class="sxs-lookup"><span data-stu-id="85bf8-139">RUNTIME_INFO_REQUEST_IA64</span></span>  
  
- <span data-ttu-id="85bf8-140">RUNTIME_INFO_REQUEST_AMD64</span><span class="sxs-lookup"><span data-stu-id="85bf8-140">RUNTIME_INFO_REQUEST_AMD64</span></span>  
  
- <span data-ttu-id="85bf8-141">RUNTIME_INFO_REQUEST_X86</span><span class="sxs-lookup"><span data-stu-id="85bf8-141">RUNTIME_INFO_REQUEST_X86</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85bf8-142">Requisiti</span><span class="sxs-lookup"><span data-stu-id="85bf8-142">Requirements</span></span>  
 <span data-ttu-id="85bf8-143">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85bf8-143">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85bf8-144">**Intestazione:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="85bf8-144">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="85bf8-145">**Libreria:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="85bf8-145">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85bf8-146">**Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85bf8-146">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85bf8-147">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="85bf8-147">See also</span></span>

- [<span data-ttu-id="85bf8-148">Funzione GetRequestedRuntimeVersion</span><span class="sxs-lookup"><span data-stu-id="85bf8-148">GetRequestedRuntimeVersion Function</span></span>](getrequestedruntimeversion-function.md)
- [<span data-ttu-id="85bf8-149">Funzione GetVersionFromProcess</span><span class="sxs-lookup"><span data-stu-id="85bf8-149">GetVersionFromProcess Function</span></span>](getversionfromprocess-function.md)
- [<span data-ttu-id="85bf8-150">Funzioni di hosting CLR deprecate</span><span class="sxs-lookup"><span data-stu-id="85bf8-150">Deprecated CLR Hosting Functions</span></span>](deprecated-clr-hosting-functions.md)
