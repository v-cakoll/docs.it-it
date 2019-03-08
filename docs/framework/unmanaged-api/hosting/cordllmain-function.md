---
title: Funzione _CorDllMain
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c509f475d5bf0105ece9791ee3e51d21c298a31f
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/08/2019
ms.locfileid: "57679307"
---
# <a name="cordllmain-function"></a><span data-ttu-id="43c65-102">\_CorDllMain (funzione)</span><span class="sxs-lookup"><span data-stu-id="43c65-102">\_CorDllMain Function</span></span>

<span data-ttu-id="43c65-103">Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="43c65-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43c65-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="43c65-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="43c65-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="43c65-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="43c65-106">[in] L'handle di istanza del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="43c65-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="43c65-107">[in] Indica il motivo per cui viene chiamata la funzione di punto di ingresso DLL.</span><span class="sxs-lookup"><span data-stu-id="43c65-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="43c65-108">Questo parametro può essere uno dei valori seguenti: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH o DLL\_processo\_DETACH.</span><span class="sxs-lookup"><span data-stu-id="43c65-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="43c65-109">Per una descrizione di questi valori, vedere il `DllMain` documentazione di Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="43c65-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="43c65-110">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="43c65-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43c65-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="43c65-111">Return Value</span></span>  
 <span data-ttu-id="43c65-112">Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="43c65-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43c65-113">Note</span><span class="sxs-lookup"><span data-stu-id="43c65-113">Remarks</span></span>  
 <span data-ttu-id="43c65-114">Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL.</span><span class="sxs-lookup"><span data-stu-id="43c65-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="43c65-115">Per gli assembly eseguibile, il caricatore chiama il [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="43c65-115">For executable assemblies, the loader calls the [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="43c65-116">Il caricatore del sistema operativo chiama questo metodo sia il punto di ingresso specificato nel file DLL.</span><span class="sxs-lookup"><span data-stu-id="43c65-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="43c65-117">Il `_CorDllMain` funzione viene chiamata direttamente dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="43c65-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="43c65-118">Per altre informazioni, vedere la sezione osservazioni nel [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="43c65-118">For additional information, see the Remarks section in the [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43c65-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="43c65-119">Requirements</span></span>  

 <span data-ttu-id="43c65-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43c65-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43c65-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="43c65-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="43c65-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="43c65-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="43c65-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43c65-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43c65-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="43c65-124">See also</span></span>

- [<span data-ttu-id="43c65-125">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="43c65-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
