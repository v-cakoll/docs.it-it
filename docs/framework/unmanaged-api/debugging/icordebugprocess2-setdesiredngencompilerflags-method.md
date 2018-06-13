---
title: Metodo ICorDebugProcess2::SetDesiredNGENCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugProcess2.SetDesiredNGENCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags
helpviewer_keywords:
- ICorDebugProcess2::SetDesiredNGENCompilerFlags method [.NET Framework debugging]
- SetDesiredNGENCompilerFlags method [.NET Framework debugging]
ms.assetid: 98320175-7c5e-4dbb-8683-86fa82e2641f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ba2b0cf7d88104eaadd434732edf3c1d4060e2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422701"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="c9917-102">Metodo ICorDebugProcess2::SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="c9917-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="c9917-103">Imposta i flag che devono essere incorporati in un'immagine precompilata affinché il runtime caricare l'immagine nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="c9917-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9917-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c9917-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c9917-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c9917-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="c9917-106">[in] Il valore di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione che specifica i flag del compilatore utilizzata per selezionare l'immagine di pre-compilata corretta.</span><span class="sxs-lookup"><span data-stu-id="c9917-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9917-107">Note</span><span class="sxs-lookup"><span data-stu-id="c9917-107">Remarks</span></span>  
 <span data-ttu-id="c9917-108">Il `SetDesiredNGENCompilerFlags` metodo specifica i flag che devono essere incorporati in un'immagine precompilata in modo che il runtime di caricarla in questo processo.</span><span class="sxs-lookup"><span data-stu-id="c9917-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="c9917-109">I flag impostati da questo metodo vengono utilizzati solo per selezionare l'immagine precompilata corretta.</span><span class="sxs-lookup"><span data-stu-id="c9917-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="c9917-110">Se l'immagine non esiste, il runtime caricherà invece l'immagine di Microsoft intermediate language (MSIL) e il compilatore di just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="c9917-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="c9917-111">In tal caso, il debugger deve comunque utilizzare il [ICorDebugModule2:: SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) per impostare i flag come desiderato per la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="c9917-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="c9917-112">Se viene caricata un'immagine, ma alcuni compilazione JIT deve essere eseguita per questa immagine (che sarà il caso se l'immagine contiene generics), i flag del compilatore specificati da di `SetDesiredNGENCompilerFlags` metodo verrà applicato a compilazione JIT aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="c9917-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="c9917-113">Il `SetDesiredNGENCompilerFlags` metodo deve essere chiamato durante la [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="c9917-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="c9917-114">Tenta di chiamare il `SetDesiredNGENCompilerFlags` metodo successivamente avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c9917-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="c9917-115">Inoltre, i tentativi di impostare i flag che non sono definite nel `CorDebugJITCompilerFlags` enumerazione o che non sono consentiti per il processo specificato avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="c9917-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9917-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c9917-116">Requirements</span></span>  
 <span data-ttu-id="c9917-117">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c9917-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9917-118">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c9917-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c9917-119">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="c9917-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c9917-120">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9917-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9917-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c9917-121">See Also</span></span>  
 [<span data-ttu-id="c9917-122">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="c9917-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [<span data-ttu-id="c9917-123">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c9917-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
