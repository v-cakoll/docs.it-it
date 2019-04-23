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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 31ff93b6935c2237a5935c4b40cc30b4129edcd0
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59230603"
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="f14e4-102">Enumerazione METAHOST_POLICY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="f14e4-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="f14e4-103">Fornisce i criteri di associazione che sono comuni per la maggior parte degli host di runtime.</span><span class="sxs-lookup"><span data-stu-id="f14e4-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="f14e4-104">Questa enumerazione viene utilizzata per la [ICLRMetaHostPolicy::](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) (metodo).</span><span class="sxs-lookup"><span data-stu-id="f14e4-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f14e4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f14e4-105">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="f14e4-106">Membri</span><span class="sxs-lookup"><span data-stu-id="f14e4-106">Members</span></span>  
  
|<span data-ttu-id="f14e4-107">Member</span><span class="sxs-lookup"><span data-stu-id="f14e4-107">Member</span></span>|<span data-ttu-id="f14e4-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f14e4-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="f14e4-109">Definisce i criteri di compatibilità elevata, che non considera qualsiasi common language runtime (CLR) caricato nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="f14e4-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="f14e4-110">Invece considera solo i runtime installati e le preferenze del componente, come derivata da file di assembly stesso, la versione compilata su dichiarata o il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f14e4-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="f14e4-111">Applica criteri di aggiornamento per il risultato di associazione di versione quando una corrispondenza esatta non viene trovata, in base al contenuto di HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="f14e4-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="f14e4-112">Ciò ha lo stesso effetto [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="f14e4-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="f14e4-113">Associazione di risultati viene restituita come se l'immagine fornita alla chiamata sono stata avviata in un nuovo processo.</span><span class="sxs-lookup"><span data-stu-id="f14e4-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="f14e4-114">Attualmente, `GetRequestedRuntime` ignora i set di runtime può essere caricati e associa a fronte del set di runtime installati.</span><span class="sxs-lookup"><span data-stu-id="f14e4-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="f14e4-115">Questo flag consente a un host determinare quale runtime di un file eseguibile verrà associato da quando viene avviata.</span><span class="sxs-lookup"><span data-stu-id="f14e4-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="f14e4-116">Viene visualizzata una finestra di dialogo di errore se `GetRequestedRuntime` non riesce a trovare un runtime che è compatibile con i parametri di input.</span><span class="sxs-lookup"><span data-stu-id="f14e4-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="f14e4-117">A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], questa finestra di dialogo di errore può assumere la forma di una finestra di dialogo funzionalità Windows in cui viene chiesto se l'utente desidera abilitare la funzionalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="f14e4-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="f14e4-118">`GetRequestedRuntime` Usa come input aggiuntivi per il processo di associazione dell'immagine del processo (e qualsiasi file di configurazione corrispondente).</span><span class="sxs-lookup"><span data-stu-id="f14e4-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="f14e4-119">Per impostazione predefinita, `GetRequestedRuntime` non eseguire il fallback per il percorso dell'immagine processo (in genere, il file EXE che è stato usato per avviare il processo) quando si determina il runtime a cui associarsi.</span><span class="sxs-lookup"><span data-stu-id="f14e4-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="f14e4-120">`GetRequestedRuntime` è necessario controllare se è installato lo SKU appropriato quando non sono disponibili informazioni nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f14e4-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="f14e4-121">Ciò consente alle applicazioni che non dispongono di file di configurazione ha esito negativo correttamente sugli SKU inferiori rispetto all'installazione predefinita di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f14e4-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="f14e4-122">Per impostazione predefinita `GetRequestedRuntime` non verifica se è installato lo SKU appropriato, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.</span><span class="sxs-lookup"><span data-stu-id="f14e4-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="f14e4-123">`GetRequestedRuntime` è necessario controllare se è installato lo SKU appropriato quando non sono disponibili informazioni nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="f14e4-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="f14e4-124">Ciò consente alle applicazioni che non dispongono di file di configurazione ha esito negativo correttamente sugli SKU inferiori rispetto all'installazione predefinita di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f14e4-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="f14e4-125">Per impostazione predefinita `GetRequestedRuntime` non verifica se è installato lo SKU appropriato, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.</span><span class="sxs-lookup"><span data-stu-id="f14e4-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="f14e4-126">`GetRequestedRuntime` deve ignorare SEM_FAILCRITICALERRORS (che viene impostato chiamando il [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) funzione) e visualizzare la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="f14e4-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="f14e4-127">Per impostazione predefinita, SEM_FAILCRITICALERRORS Elimina la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="f14e4-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="f14e4-128">Sono stata ereditata da un altro processo e l'errore invisibile all'utente può essere inaccettabile nel proprio scenario.</span><span class="sxs-lookup"><span data-stu-id="f14e4-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f14e4-129">Note</span><span class="sxs-lookup"><span data-stu-id="f14e4-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f14e4-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f14e4-130">Requirements</span></span>  
 <span data-ttu-id="f14e4-131">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f14e4-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f14e4-132">**Intestazione:** Metahost.h</span><span class="sxs-lookup"><span data-stu-id="f14e4-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="f14e4-133">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="f14e4-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f14e4-134">**Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f14e4-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14e4-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f14e4-135">See also</span></span>

- [<span data-ttu-id="f14e4-136">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="f14e4-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
- [<span data-ttu-id="f14e4-137">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="f14e4-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
