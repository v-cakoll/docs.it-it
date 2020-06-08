---
title: Interfaccia ICLRMetaHost
ms.date: 03/30/2017
api_name:
- ICLRMetaHost
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost
helpviewer_keywords:
- ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: c627fcdd-fc4f-4b1c-8e91-df8536f627d8
topic_type:
- apiref
ms.openlocfilehash: bb7c3659930f308328cba121c06a88cb6a95eb26
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504160"
---
# <a name="iclrmetahost-interface"></a><span data-ttu-id="51dac-102">Interfaccia ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="51dac-102">ICLRMetaHost Interface</span></span>
<span data-ttu-id="51dac-103">Fornisce metodi che restituiscono una versione specifica del Common Language Runtime (CLR) in base al relativo numero di versione, elencare tutti CLR installati, elencare tutti i runtime caricati in un processo specifico, individuare la versione CLR utilizzata per compilare un assembly, uscire da un processo con un arresto del runtime pulito ed eseguire query sull'associazione API legacy.</span><span class="sxs-lookup"><span data-stu-id="51dac-103">Provides methods that return a specific version of the common language runtime (CLR) based on its version number, list all installed CLRs, list all runtimes that are loaded in a specified process, discover the CLR version used to compile an assembly, exit a process with a clean runtime shutdown, and query legacy API binding.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="51dac-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="51dac-104">Methods</span></span>  
  
|<span data-ttu-id="51dac-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="51dac-105">Method</span></span>|<span data-ttu-id="51dac-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="51dac-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="51dac-107">Metodo EnumerateInstalledRuntimes</span><span class="sxs-lookup"><span data-stu-id="51dac-107">EnumerateInstalledRuntimes Method</span></span>](iclrmetahost-enumerateinstalledruntimes-method.md)|<span data-ttu-id="51dac-108">Restituisce un'enumerazione che contiene un puntatore a interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) valido per ogni versione CLR installata in un computer.</span><span class="sxs-lookup"><span data-stu-id="51dac-108">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR version that is installed on a computer.</span></span>|  
|[<span data-ttu-id="51dac-109">Metodo EnumerateLoadedRuntimes</span><span class="sxs-lookup"><span data-stu-id="51dac-109">EnumerateLoadedRuntimes Method</span></span>](iclrmetahost-enumerateloadedruntimes-method.md)|<span data-ttu-id="51dac-110">Restituisce un'enumerazione che contiene un puntatore a interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) valido per ogni CLR caricato in un determinato processo.</span><span class="sxs-lookup"><span data-stu-id="51dac-110">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each CLR that is loaded in a given process.</span></span> <span data-ttu-id="51dac-111">Questo metodo sostituisce [GetVersionFromProcess](getversionfromprocess-function.md).</span><span class="sxs-lookup"><span data-stu-id="51dac-111">This method supersedes [GetVersionFromProcess](getversionfromprocess-function.md).</span></span>|  
|[<span data-ttu-id="51dac-112">Metodo ExitProcess</span><span class="sxs-lookup"><span data-stu-id="51dac-112">ExitProcess Method</span></span>](iclrmetahost-exitprocess-method.md)|<span data-ttu-id="51dac-113">Tenta di arrestare correttamente tutti i runtime caricati, quindi termina il processo.</span><span class="sxs-lookup"><span data-stu-id="51dac-113">Attempts to shut down all loaded runtimes gracefully and then terminates the process.</span></span> <span data-ttu-id="51dac-114">Sostituisce la funzione [CorExitProcess](corexitprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="51dac-114">Supersedes the [CorExitProcess](corexitprocess-function.md) function.</span></span>|  
|[<span data-ttu-id="51dac-115">Metodo GetRuntime</span><span class="sxs-lookup"><span data-stu-id="51dac-115">GetRuntime Method</span></span>](iclrmetahost-getruntime-method.md)|<span data-ttu-id="51dac-116">Ottiene l'interfaccia [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) che corrisponde a una particolare versione di CLR.</span><span class="sxs-lookup"><span data-stu-id="51dac-116">Gets the [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface that corresponds to a particular CLR version.</span></span> <span data-ttu-id="51dac-117">Questo metodo sostituisce la funzione [CorBindToRuntimeEx](corbindtoruntimeex-function.md) utilizzata con il flag [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="51dac-117">This method supersedes the [CorBindToRuntimeEx](corbindtoruntimeex-function.md) function used with the [STARTUP_LOADER_SAFEMODE](startup-flags-enumeration.md) flag.</span></span>|  
|[<span data-ttu-id="51dac-118">Metodo GetVersionFromFile</span><span class="sxs-lookup"><span data-stu-id="51dac-118">GetVersionFromFile Method</span></span>](iclrmetahost-getversionfromfile-method.md)|<span data-ttu-id="51dac-119">Ottiene la versione originale del .NET Framework di compilazione dell'assembly (archiviata nei metadati), dato il percorso del file.</span><span class="sxs-lookup"><span data-stu-id="51dac-119">Gets the assembly's original .NET Framework compilation version (stored in the metadata), given its file path.</span></span> <span data-ttu-id="51dac-120">Questo metodo sostituisce [GetFileVersion](getfileversion-function.md).</span><span class="sxs-lookup"><span data-stu-id="51dac-120">This method supersedes [GetFileVersion](getfileversion-function.md).</span></span>|  
|[<span data-ttu-id="51dac-121">Metodo QueryLegacyV2RuntimeBinding</span><span class="sxs-lookup"><span data-stu-id="51dac-121">QueryLegacyV2RuntimeBinding Method</span></span>](iclrmetahost-querylegacyv2runtimebinding-method.md)|<span data-ttu-id="51dac-122">Restituisce un'interfaccia che rappresenta un runtime a cui sono stati associati i criteri di attivazione legacy, ad esempio usando l' `useLegacyV2RuntimeActivationPolicy` attributo nella voce del file di configurazione degli [ \<startup> elementi](../../configure-apps/file-schema/startup/startup-element.md) , usando direttamente le API di attivazione legacy oppure chiamando il metodo [ICLRRuntimeInfo:: BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="51dac-122">Returns an interface that represents a runtime to which legacy activation policy has been bound, for example by using the `useLegacyV2RuntimeActivationPolicy` attribute on the [\<startup> Element](../../configure-apps/file-schema/startup/startup-element.md) configuration file entry, by direct use of the legacy activation APIs, or by calling the [ICLRRuntimeInfo::BindAsLegacyV2Runtime](iclrruntimeinfo-bindaslegacyv2runtime-method.md) method.</span></span>|  
|[<span data-ttu-id="51dac-123">Metodo RequestRuntimeLoadedNotification</span><span class="sxs-lookup"><span data-stu-id="51dac-123">RequestRuntimeLoadedNotification Method</span></span>](iclrmetahost-requestruntimeloadednotification-method.md)|<span data-ttu-id="51dac-124">Garantisce un callback al puntatore a funzione specificato quando una versione CLR viene caricata per la prima volta, ma non ancora avviata.</span><span class="sxs-lookup"><span data-stu-id="51dac-124">Guarantees a callback to the specified function pointer when a CLR version is first loaded, but not yet started.</span></span> <span data-ttu-id="51dac-125">Questo metodo sostituisce [LockClrVersion](lockclrversion-function.md)</span><span class="sxs-lookup"><span data-stu-id="51dac-125">This method supersedes [LockClrVersion](lockclrversion-function.md)</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51dac-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="51dac-126">Remarks</span></span>  
 <span data-ttu-id="51dac-127">L'unico modo per ottenere un'istanza di questa interfaccia consiste nel chiamare la funzione [CLRCreateInstance](clrcreateinstance-function.md) come segue:</span><span class="sxs-lookup"><span data-stu-id="51dac-127">The only way to get an instance of this interface is by calling the [CLRCreateInstance](clrcreateinstance-function.md) function as follows:</span></span>  
  
```cpp  
ICLRMetaHost *pMetaHost = NULL;  
HRESULT hr = CLRCreateInstance(CLSID_CLRMetaHost,  
                   IID_ICLRMetaHost, (LPVOID*)&pMetaHost);  
```  
  
## <a name="requirements"></a><span data-ttu-id="51dac-128">Requisiti</span><span class="sxs-lookup"><span data-stu-id="51dac-128">Requirements</span></span>  
 <span data-ttu-id="51dac-129">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51dac-129">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51dac-130">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="51dac-130">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="51dac-131">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="51dac-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="51dac-132">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51dac-132">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51dac-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51dac-133">See also</span></span>

- [<span data-ttu-id="51dac-134">Interfacce di hosting</span><span class="sxs-lookup"><span data-stu-id="51dac-134">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="51dac-135">Hosting</span><span class="sxs-lookup"><span data-stu-id="51dac-135">Hosting</span></span>](index.md)
