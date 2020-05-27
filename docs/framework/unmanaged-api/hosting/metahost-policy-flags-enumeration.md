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
ms.openlocfilehash: bb40ed65a2e34f1bf293e4c4c842d7db63d2eaa5
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008443"
---
# <a name="metahost_policy_flags-enumeration"></a><span data-ttu-id="22970-102">Enumerazione METAHOST_POLICY_FLAGS</span><span class="sxs-lookup"><span data-stu-id="22970-102">METAHOST_POLICY_FLAGS Enumeration</span></span>
<span data-ttu-id="22970-103">Fornisce criteri di associazione comuni alla maggior parte degli host di Runtime.</span><span class="sxs-lookup"><span data-stu-id="22970-103">Provides binding policies that are common to most runtime hosts.</span></span> <span data-ttu-id="22970-104">Questa enumerazione viene utilizzata dal metodo [ICLRMetaHostPolicy:: GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) .</span><span class="sxs-lookup"><span data-stu-id="22970-104">This enumeration is used by the [ICLRMetaHostPolicy::GetRequestedRuntime](iclrmetahostpolicy-getrequestedruntime-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22970-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="22970-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="22970-106">Membri</span><span class="sxs-lookup"><span data-stu-id="22970-106">Members</span></span>  
  
|<span data-ttu-id="22970-107">Membro</span><span class="sxs-lookup"><span data-stu-id="22970-107">Member</span></span>|<span data-ttu-id="22970-108">Descrizione</span><span class="sxs-lookup"><span data-stu-id="22970-108">Description</span></span>|  
|------------|-----------------|  
|`METAHOST_POLICY_HIGHCOMPAT`|<span data-ttu-id="22970-109">Definisce i criteri di compatibilità elevata, che non considera alcun Common Language Runtime (CLR) caricato nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="22970-109">Defines the high-compatibility policy, which does not consider any common language runtime (CLR) that is loaded into the current process.</span></span> <span data-ttu-id="22970-110">Considera invece solo i CLR installati e le preferenze del componente, come derivato dal file di assembly stesso, dalla versione predefinita dichiarata o dal file di configurazione.</span><span class="sxs-lookup"><span data-stu-id="22970-110">Instead, it considers only the installed CLRs and the preferences of the component, as derived from the assembly file itself, the declared built-against version, or the configuration file.</span></span>|  
|`METAHOST_POLICY_APPLY_UPGRADE_POLICY`|<span data-ttu-id="22970-111">Applica i criteri di aggiornamento al risultato dell'associazione della versione quando non viene trovata una corrispondenza esatta, in base al contenuto di HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft \\ . NETFramework\Policy\Upgrades.</span><span class="sxs-lookup"><span data-stu-id="22970-111">Applies upgrade policy to the version bind result when an exact match is not found, based on the contents of HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\\.NETFramework\Policy\Upgrades.</span></span> <span data-ttu-id="22970-112">Questa operazione ha lo stesso effetto di [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="22970-112">This has the same effect as [RUNTIME_INFO_UPGRADE_VERSION](runtime-info-flags-enumeration.md).</span></span>|  
|`METAHOST_POLICY_EMULATE_EXE_LAUNCH`|<span data-ttu-id="22970-113">I risultati dell'associazione vengono restituiti come se l'immagine fornita alla chiamata venisse avviata in un nuovo processo.</span><span class="sxs-lookup"><span data-stu-id="22970-113">Binding results are returned as if the image provided to the call were launched in a new process.</span></span> <span data-ttu-id="22970-114">Attualmente, `GetRequestedRuntime` Ignora il set di Runtime caricabili e viene associato al set di runtime installati.</span><span class="sxs-lookup"><span data-stu-id="22970-114">Currently, `GetRequestedRuntime` ignores the set of loadable runtimes and binds against the set of installed runtimes.</span></span> <span data-ttu-id="22970-115">Questo flag consente a un host di determinare a quale Runtime verrà associato un file EXE quando viene avviato.</span><span class="sxs-lookup"><span data-stu-id="22970-115">This flag allows a host to determine which runtime an EXE will bind to when it is launched.</span></span>|  
|`METAHOST_POLICY_SHOW_ERROR_DIALOG`|<span data-ttu-id="22970-116">Viene visualizzata una finestra di dialogo di errore se `GetRequestedRuntime` non è in grado di trovare un runtime compatibile con i parametri di input.</span><span class="sxs-lookup"><span data-stu-id="22970-116">An error dialog box is displayed if `GetRequestedRuntime` is unable to find a runtime that is compatible with the input parameters.</span></span> <span data-ttu-id="22970-117">A partire da .NET Framework 4,5, questa finestra di dialogo di errore può assumere il formato di una finestra di dialogo funzionalità di Windows che chiede se l'utente vuole abilitare la funzionalità appropriata.</span><span class="sxs-lookup"><span data-stu-id="22970-117">Beginning with the .NET Framework 4.5, this error dialog box can take the form of a Windows feature dialog box that asks whether the user would like to enable the appropriate feature.</span></span>|  
|`METAHOST_POLICY_USE_PROCESS_IMAGE_PATH`|<span data-ttu-id="22970-118">`GetRequestedRuntime`Usa l'immagine del processo e qualsiasi file di configurazione corrispondente come input aggiuntivo per il processo di associazione.</span><span class="sxs-lookup"><span data-stu-id="22970-118">`GetRequestedRuntime` uses the process image (and any corresponding configuration file) as additional input to the binding process.</span></span> <span data-ttu-id="22970-119">Per impostazione predefinita, non `GetRequestedRuntime` esegue il fallback al percorso dell'immagine del processo (in genere, il file exe usato per avviare il processo) quando si determina il runtime a cui eseguire l'associazione.</span><span class="sxs-lookup"><span data-stu-id="22970-119">By default, `GetRequestedRuntime` does not fall back to the process image path (typically, the EXE that was used to launch the process) when determining the runtime to bind to.</span></span>|  
|`METAHOST_POLICY_ENSURE_SKU_SUPPORTED`|<span data-ttu-id="22970-120">`GetRequestedRuntime`è necessario verificare se lo SKU appropriato è installato quando nel file di configurazione non sono disponibili informazioni.</span><span class="sxs-lookup"><span data-stu-id="22970-120">`GetRequestedRuntime` must check whether the appropriate SKU is installed when no information is available in the configuration file.</span></span> <span data-ttu-id="22970-121">In questo modo, le applicazioni che non dispongono di file di configurazione avranno esito negativo correttamente su SKU più piccoli rispetto all'installazione predefinita del .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="22970-121">This allows applications that do not have configuration files to fail gracefully on smaller SKUs than the default installation of the .NET Framework.</span></span> <span data-ttu-id="22970-122">Per impostazione predefinita, non `GetRequestedRuntime` Controlla se lo SKU appropriato è installato, a meno che l'attributo SKU non sia specificato nell'elemento file di configurazione `<supportedRuntime />` .</span><span class="sxs-lookup"><span data-stu-id="22970-122">By default, `GetRequestedRuntime` does not check whether the appropriate SKU is installed unless the SKU attribute is specified in the configuration file `<supportedRuntime />` element.</span></span>|  
|`METAHOST_POLICY_IGNORE_ERROR_MODE`|<span data-ttu-id="22970-123">`GetRequestedRuntime`deve ignorare SEM_FAILCRITICALERRORS (che viene impostato chiamando la funzione [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) ) e visualizzare la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="22970-123">`GetRequestedRuntime` should ignore SEM_FAILCRITICALERRORS (which is set by calling the [SetErrorMode](/windows/win32/api/errhandlingapi/nf-errhandlingapi-seterrormode) function), and show the error dialog box.</span></span> <span data-ttu-id="22970-124">Per impostazione predefinita, SEM_FAILCRITICALERRORS elimina la finestra di dialogo di errore.</span><span class="sxs-lookup"><span data-stu-id="22970-124">By default, SEM_FAILCRITICALERRORS suppresses the error dialog box.</span></span> <span data-ttu-id="22970-125">Potrebbe essere stata ereditata da un altro processo e l'errore invisibile all'utente potrebbe essere indesiderato nello scenario.</span><span class="sxs-lookup"><span data-stu-id="22970-125">It may have been inherited from another process, and the silent error may be undesirable in your scenario.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="22970-126">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="22970-126">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="22970-127">Requisiti</span><span class="sxs-lookup"><span data-stu-id="22970-127">Requirements</span></span>  
 <span data-ttu-id="22970-128">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="22970-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22970-129">**Intestazione:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="22970-129">**Header:** Metahost.h</span></span>  
  
 <span data-ttu-id="22970-130">**Libreria:** Incluso come risorsa in MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="22970-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="22970-131">**Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22970-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22970-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22970-132">See also</span></span>

- [<span data-ttu-id="22970-133">Enumerazioni di hosting</span><span class="sxs-lookup"><span data-stu-id="22970-133">Hosting Enumerations</span></span>](hosting-enumerations.md)
- [<span data-ttu-id="22970-134">Metodo GetRequestedRuntime</span><span class="sxs-lookup"><span data-stu-id="22970-134">GetRequestedRuntime Method</span></span>](iclrmetahostpolicy-getrequestedruntime-method.md)
