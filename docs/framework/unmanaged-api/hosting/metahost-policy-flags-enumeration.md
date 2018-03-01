---
title: Enumerazione METAHOST_POLICY_FLAGS
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 80abed08cc7659d4218dce445be81481bb5a665b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="metahostpolicyflags-enumeration"></a><span data-ttu-id="7fd19-102">Enumerazione METAHOST_POLICY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="7fd19-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="7fd19-103">Fornisce criteri di associazione che sono comuni per la maggior parte degli host di runtime.</span><span class="sxs-lookup"><span data-stu-id="7fd19-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="7fd19-104">Questa enumerazione viene utilizzata per la [ICLRMetaHostPolicy::](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="7fd19-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fd19-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7fd19-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="7fd19-106">Membri</span><span class="sxs-lookup"><span data-stu-id="7fd19-106">Members</span></span>  
  
|<span data-ttu-id="7fd19-107">Membro</span><span class="sxs-lookup"><span data-stu-id="7fd19-107">Member</span></span>|<span data-ttu-id="7fd19-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7fd19-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="7fd19-109">Definisce i criteri di compatibilità elevata, che non vengono considerate qualsiasi common language runtime (CLR) caricato nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="7fd19-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="7fd19-110">Invece presi in considerazione solo i runtime installati e le preferenze del componente, derivato da file di assembly stesso, la versione compilata contro dichiarata o il file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7fd19-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="7fd19-111">Applica i criteri di aggiornamento per il risultato di associazione della versione quando una corrispondenza esatta non viene trovata, in base al contenuto di HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\. NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="7fd19-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="7fd19-112">Questo è lo stesso effetto [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="7fd19-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](../../../../docs/framework/unmanaged-api/hosting/runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="7fd19-113">Associazione vengono restituiti come se l'immagine fornita per la chiamata avviata in un nuovo processo.</span><span class="sxs-lookup"><span data-stu-id="7fd19-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="7fd19-114">Attualmente, `GetRequestedRuntime` ignora il set di runtime caricabili e associazioni rispetto al set dei runtime installati.</span><span class="sxs-lookup"><span data-stu-id="7fd19-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="7fd19-115">Questo flag consente a un host determinare il runtime a cui verrà associato a un EXE quando viene avviata.</span><span class="sxs-lookup"><span data-stu-id="7fd19-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="7fd19-116">Viene visualizzata una finestra di dialogo di errore se `GetRequestedRuntime` non riesce a trovare un runtime che è compatibile con i parametri di input.</span><span class="sxs-lookup"><span data-stu-id="7fd19-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="7fd19-117">A partire dal [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], questa finestra di dialogo di errore può essere in forma di una finestra di dialogo per la funzionalità Windows in cui viene chiesto se si desidera abilitare la funzionalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="7fd19-117">Beginning with the [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="7fd19-118">`GetRequestedRuntime`Usa l'immagine del processo (e qualsiasi file di configurazione corrispondente) come input aggiuntivi per il processo di associazione.</span><span class="sxs-lookup"><span data-stu-id="7fd19-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="7fd19-119">Per impostazione predefinita, `GetRequestedRuntime` non eseguire il fallback per il percorso dell'immagine di processo (in genere, il file EXE che è stato utilizzato per avviare il processo) quando si determina il runtime da associare.</span><span class="sxs-lookup"><span data-stu-id="7fd19-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="7fd19-120">`GetRequestedRuntime`è necessario controllare se è installata la SKU appropriata quando non sono disponibili informazioni nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7fd19-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="7fd19-121">Ciò consente alle applicazioni che non contengono i file di configurazione avrà esito negativo normalmente SKU più piccoli rispetto all'installazione predefinita di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fd19-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="7fd19-122">Per impostazione predefinita, `GetRequestedRuntime` non verifica se è installata la SKU appropriata, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.</span><span class="sxs-lookup"><span data-stu-id="7fd19-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="7fd19-123">`GetRequestedRuntime`è necessario controllare se è installata la SKU appropriata quando non sono disponibili informazioni nel file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="7fd19-123">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="7fd19-124">Ciò consente alle applicazioni che non contengono i file di configurazione avrà esito negativo normalmente SKU più piccoli rispetto all'installazione predefinita di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="7fd19-124">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="7fd19-125">Per impostazione predefinita, `GetRequestedRuntime` non verifica se è installata la SKU appropriata, a meno che l'attributo SKU è specificato nel file di configurazione `<supportedRuntime />` elemento.</span><span class="sxs-lookup"><span data-stu-id="7fd19-125">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="7fd19-126">`GetRequestedRuntime`deve essere ignorato SEM_FAILCRITICALERRORS (che viene impostato chiamando la [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) funzione) e visualizzare la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="7fd19-126">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) function), and show the error dialog box.</span></span> <span data-ttu-id="7fd19-127">Per impostazione predefinita, SEM_FAILCRITICALERRORS Elimina la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="7fd19-127">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="7fd19-128">Sono stata ereditata da un altro processo e l'errore invisibile all'utente potrebbe essere indesiderata nello scenario.</span><span class="sxs-lookup"><span data-stu-id="7fd19-128">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7fd19-129">Note</span><span class="sxs-lookup"><span data-stu-id="7fd19-129">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7fd19-130">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7fd19-130">Requirements</span></span>  
 <span data-ttu-id="7fd19-131">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fd19-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fd19-132">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="7fd19-132">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="7fd19-133">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7fd19-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7fd19-134">**Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fd19-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fd19-135">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7fd19-135">See Also</span></span>  
 [<span data-ttu-id="7fd19-136">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="7fd19-136">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)  
 [<span data-ttu-id="7fd19-137">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="7fd19-137">GetRequestedRuntime Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-getrequestedruntime-method.md)
