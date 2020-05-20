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
ms.openlocfilehash: 3b2322f708afed08172f87e843c225aa9c60d9d3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616606"
---
# <a name="_cordllmain-function"></a><span data-ttu-id="f8fa7-102">\_CorDllMain (funzione)</span><span class="sxs-lookup"><span data-stu-id="f8fa7-102">\_CorDllMain Function</span></span>

<span data-ttu-id="f8fa7-103">Inizializza il Common Language Runtime (CLR), individua il punto di ingresso gestito nell'intestazione CLR dell'assembly DLL e avvia l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-103">Initializes the common language runtime (CLR), locates the managed entry point in the DLL assembly's CLR header, and begins execution.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8fa7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f8fa7-104">Syntax</span></span>  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f8fa7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f8fa7-105">Parameters</span></span>  
 `hInst`  
 <span data-ttu-id="f8fa7-106">in Handle dell'istanza del modulo caricato.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-106">[in] The instance handle of the loaded module.</span></span>  
  
 `dwReason`  
 <span data-ttu-id="f8fa7-107">in Indica il motivo per cui viene chiamata la funzione del punto di ingresso della DLL.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-107">[in]Indicates why the DLL entry-point function is being called.</span></span> <span data-ttu-id="f8fa7-108">Questo parametro può essere uno dei valori seguenti: DLL \_ PROCESS_ATTACH, \_ collegamento thread dll \_ , \_ collegamento thread dll \_ o \_ disconnessione processo dll \_ .</span><span class="sxs-lookup"><span data-stu-id="f8fa7-108">This parameter can be one of the following values: DLL\_PROCESS_ATTACH, DLL\_THREAD\_ATTACH, DLL\_THREAD\_ATTACH, or DLL\_PROCESS\_DETACH.</span></span> <span data-ttu-id="f8fa7-109">Per una descrizione di questi valori, vedere la `DllMain` documentazione in Platform SDK.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-109">For descriptions of these values, see the `DllMain` documentation in the Platform SDK.</span></span>  
  
 `lpReserved`  
 <span data-ttu-id="f8fa7-110">[in] Non utilizzato.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-110">[in] Unused.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f8fa7-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="f8fa7-111">Return Value</span></span>  
 <span data-ttu-id="f8fa7-112">Questo metodo restituisce `true` per l'esito positivo e `false` se si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-112">This method returns `true` for success and `false` if an error occurs.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f8fa7-113">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="f8fa7-113">Remarks</span></span>  
 <span data-ttu-id="f8fa7-114">Questa funzione viene chiamata dal caricatore del sistema operativo per gli assembly DLL.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-114">This function is called by the operating system loader for DLL assemblies.</span></span> <span data-ttu-id="f8fa7-115">Per gli assembly eseguibili, il caricatore chiama invece la funzione [ \_ CorExeMain](corexemain-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f8fa7-115">For executable assemblies, the loader calls the [\_CorExeMain](corexemain-function.md) function instead.</span></span>  
  
 <span data-ttu-id="f8fa7-116">Il caricatore del sistema operativo chiama questo metodo indipendentemente dal punto di ingresso specificato nel file DLL.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-116">The operating system loader calls this method regardless of the entry point specified in the DLL file.</span></span>  
  
<span data-ttu-id="f8fa7-117">La `_CorDllMain` funzione viene chiamata direttamente dal caricatore del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="f8fa7-117">The `_CorDllMain` function is called directly by the operating system loader.</span></span>
  
 <span data-ttu-id="f8fa7-118">Per ulteriori informazioni, vedere la sezione osservazioni nell'argomento [ \_ CorValidateImage](corvalidateimage-function.md) .</span><span class="sxs-lookup"><span data-stu-id="f8fa7-118">For additional information, see the Remarks section in the [\_CorValidateImage](corvalidateimage-function.md) topic.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f8fa7-119">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f8fa7-119">Requirements</span></span>  

 <span data-ttu-id="f8fa7-120">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8fa7-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8fa7-121">**Intestazione:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f8fa7-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8fa7-122">**Libreria:** Incluso come risorsa in MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f8fa7-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8fa7-123">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8fa7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8fa7-124">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f8fa7-124">See also</span></span>

- [<span data-ttu-id="f8fa7-125">Funzioni statiche globali dei metadati</span><span class="sxs-lookup"><span data-stu-id="f8fa7-125">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
