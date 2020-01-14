---
title: Enumerazione METAHOST_POLICY_FLAGS
ms.date: 03/30/2017
api_name:
- METAHOST_POLICY_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- METAHOST_POLICY_FLAGS
helpviewer_keywords:
- METAHOST_POLICY_FLAGS enumeration [.NET Framework hosting]
ms.assetid: 3bb4b526-0118-42e2-ba59-c95648528ce9
topic_type:
- apiref
ms.openlocfilehash: 048286fb9e1af34cd964fb5b21892778f9575d2c
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "75938200"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="84b64-102">Enumerazione METAHOST_POLICY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="84b64-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="84b64-103">Fornisce criteri di associazione comuni alla maggior parte degli host di Runtime.</span><span class="sxs-lookup"><span data-stu-id="84b64-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="84b64-104">Questa enumerazione viene utilizzata dal metodo [ICLRMetaHostPolicy:: GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="84b64-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="84b64-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="84b64-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    METAHOST_POLICY_HIGHCOMPAT              = 0x00,  
    METAHOST_POLICY_APPLY_UPGRADE_POLICY    = 0x08,  
    METAHOST_POLICY_EMULATE_EXE_LAUNCH      = 0x10,  
    METAHOST_POLICY_SHOW_ERROR_DIALOG       = 0x20,  
    METAHOST_POLICY_USE_PROCESS_IMAGE_PATH  = 0x40,  
    METAHOST_POLICY_ENSURE_SKU_SUPPORTED    = 0x80,  
    METAHOST_POLICY_IGNORE_ERROR_MODE       = 0x1000  
  
} METAHOST_POLICY_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="84b64-106">Membri</span><span class="sxs-lookup"><span data-stu-id="84b64-106">Members</span></span>  
  
|<span data-ttu-id="84b64-107">Member</span><span class="sxs-lookup"><span data-stu-id="84b64-107">Member</span></span>|<span data-ttu-id="84b64-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="84b64-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="84b64-109">Definisce i criteri di compatibilità elevata, che non considera alcun Common Language Runtime (CLR) caricato nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="84b64-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="84b64-110">Considera invece solo i CLR installati e le preferenze del componente, come derivato dal file di assembly stesso, dalla versione predefinita dichiarata o dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="84b64-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="84b64-111">Applica i criteri di aggiornamento al risultato dell'associazione della versione quando non viene trovata una corrispondenza esatta, in base al contenuto di HKEY_LOCAL_MACHINE\\\SOFTWARE\Microsoft. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="84b64-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="84b64-112">Questa operazione ha lo stesso effetto di [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="84b64-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="84b64-113">I risultati dell'associazione vengono restituiti come se l'immagine fornita alla chiamata venisse avviata in un nuovo processo.</span><span class="sxs-lookup"><span data-stu-id="84b64-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="84b64-114">Attualmente, `GetRequestedRuntime` ignora il set di Runtime caricabili e viene associato al set di runtime installati.</span><span class="sxs-lookup"><span data-stu-id="84b64-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="84b64-115">Questo flag consente a un host di determinare a quale Runtime verrà associato un file EXE quando viene avviato.</span><span class="sxs-lookup"><span data-stu-id="84b64-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="84b64-116">Se `GetRequestedRuntime` non è in grado di trovare un runtime compatibile con i parametri di input, viene visualizzata una finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="84b64-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="84b64-117">A partire da .NET Framework 4,5, questa finestra di dialogo di errore può assumere il formato di una finestra di dialogo funzionalità di Windows che chiede se l'utente vuole abilitare la funzionalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="84b64-117">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="84b64-118">`GetRequestedRuntime` usa l'immagine di processo (e qualsiasi file di configurazione corrispondente) come input aggiuntivo per il processo di associazione.</span><span class="sxs-lookup"><span data-stu-id="84b64-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="84b64-119">Per impostazione predefinita, `GetRequestedRuntime` non viene eseguito il fallback al percorso dell'immagine del processo (in genere, il file EXE utilizzato per avviare il processo) quando si determina il runtime a cui eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="84b64-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="84b64-120">`GetRequestedRuntime` necessario controllare se lo SKU appropriato viene installato quando nel file di configurazione non sono disponibili informazioni.</span><span class="sxs-lookup"><span data-stu-id="84b64-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="84b64-121">In questo modo, le applicazioni che non dispongono di file di configurazione avranno esito negativo correttamente su SKU più piccoli rispetto all'installazione predefinita del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="84b64-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="84b64-122">Per impostazione predefinita, `GetRequestedRuntime` non controlla se lo SKU appropriato è installato, a meno che l'attributo SKU non sia specificato nel file di configurazione `<supportedRuntime />` elemento.</span><span class="sxs-lookup"><span data-stu-id="84b64-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="84b64-123">`GetRequestedRuntime` deve ignorare SEM_FAILCRITICALERRORS, che viene impostato chiamando la funzione [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) , e visualizzare la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="84b64-123">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function), and show the error dialog box.</span></span> <span data-ttu-id="84b64-124">Per impostazione predefinita, SEM_FAILCRITICALERRORS elimina la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="84b64-124">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="84b64-125">Potrebbe essere stata ereditata da un altro processo e l'errore invisibile all'utente potrebbe essere indesiderato nello scenario.</span><span class="sxs-lookup"><span data-stu-id="84b64-125">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="84b64-126">Note</span><span class="sxs-lookup"><span data-stu-id="84b64-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="84b64-127">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="84b64-127">Requirements</span></span>  
 <span data-ttu-id="84b64-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84b64-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84b64-129">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="84b64-129">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="84b64-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="84b64-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="84b64-131">**Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84b64-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84b64-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84b64-132">See also</span></span>

- [<span data-ttu-id="84b64-133">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="84b64-133">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="84b64-134">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="84b64-134">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
