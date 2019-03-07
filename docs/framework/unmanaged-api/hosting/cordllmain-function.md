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
ms.openlocfilehash: e3c529e77cad16f0bde12e34491829b58add17aa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57500381"
---
# <a name="cordllmain-function"></a><span data-ttu-id="579c6-102">Funzione _CorDllMain</span><span class="sxs-lookup"><span data-stu-id="579c6-102">_CorDllMain Function</span></span>
<span data-ttu-id="579c6-103">Consente di inizializzare common language runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e inizia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="579c6-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="579c6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="579c6-104">Syntax</span></span>  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="579c6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="579c6-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="579c6-106">[in] L'handle di istanza del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="579c6-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="579c6-107">[in] Indica il motivo per cui viene chiamata la funzione di punto di ingresso DLL.</span><span class="sxs-lookup"><span data-stu-id="579c6-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="579c6-108">Questo parametro può essere uno dei valori seguenti: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH o DLL_PROCESS_DETACH.</span><span class="sxs-lookup"><span data-stu-id="579c6-108">This parameter can be one of the following values: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH, or DLL_PROCESS_DETACH.</span></span> <span data-ttu-id="579c6-109">Per una descrizione di questi valori, vedere il `DllMain` documentazione di Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="579c6-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="579c6-110">[in] Non usato.</span><span class="sxs-lookup"><span data-stu-id="579c6-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="579c6-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="579c6-111">Return Value</span></span>  
 <span data-ttu-id="579c6-112">Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="579c6-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="579c6-113">Note</span><span class="sxs-lookup"><span data-stu-id="579c6-113">Remarks</span></span>  
 <span data-ttu-id="579c6-114">Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL.</span><span class="sxs-lookup"><span data-stu-id="579c6-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="579c6-115">Per gli assembly eseguibile, il caricatore chiama il [CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funzione.</span><span class="sxs-lookup"><span data-stu-id="579c6-115">For executable assemblies, the loader calls the [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="579c6-116">Il caricatore del sistema operativo chiama questo metodo sia il punto di ingresso specificato nel file DLL.</span><span class="sxs-lookup"><span data-stu-id="579c6-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="579c6-117">Il `_CorDllMain` funzione viene chiamata direttamente dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="579c6-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="579c6-118">Per altre informazioni, vedere la sezione osservazioni nel [CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) argomento.</span><span class="sxs-lookup"><span data-stu-id="579c6-118">For additional information, see the Remarks section in the [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="579c6-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="579c6-119">Requirements</span></span>  
 <span data-ttu-id="579c6-120">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="579c6-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="579c6-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="579c6-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="579c6-122">**Libreria:** Inclusa come risorsa in Mscoree. dll</span><span class="sxs-lookup"><span data-stu-id="579c6-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="579c6-123">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="579c6-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="579c6-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="579c6-124">See also</span></span>
- [<span data-ttu-id="579c6-125">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="579c6-125">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
