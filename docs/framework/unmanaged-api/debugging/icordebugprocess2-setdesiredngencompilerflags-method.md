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
ms.openlocfilehash: bc0dde4f2455ed45ddf8ca1efefa7ab67ba04f6f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660775"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="65290-102">Metodo ICorDebugProcess2::SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="65290-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="65290-103">Imposta i flag che devono essere incorporati in un'immagine precompilata affinché il runtime di caricare tale immagine nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="65290-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65290-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="65290-104">Syntax</span></span>  
  
```  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="65290-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="65290-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="65290-106">[in] Valore di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumerazione che specifica i flag del compilatore usato per selezionare l'immagine di pre-compilata corretta.</span><span class="sxs-lookup"><span data-stu-id="65290-106">[in] A value of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65290-107">Note</span><span class="sxs-lookup"><span data-stu-id="65290-107">Remarks</span></span>  
 <span data-ttu-id="65290-108">Il `SetDesiredNGENCompilerFlags` metodo specifica i flag che devono essere incorporati in un'immagine precompilata in modo che il runtime caricherà l'immagine in questo processo.</span><span class="sxs-lookup"><span data-stu-id="65290-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="65290-109">I flag impostati da questo metodo vengono utilizzati solo per selezionare l'immagine corretta precompilata.</span><span class="sxs-lookup"><span data-stu-id="65290-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="65290-110">Se l'immagine non esiste, il runtime caricherà invece l'immagine di Microsoft intermediate language (MSIL) e il compilatore JIT just-in-time.</span><span class="sxs-lookup"><span data-stu-id="65290-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="65290-111">In tal caso, il debugger deve ancora utilizzare il [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) metodo per impostare i flag desiderati per la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="65290-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="65290-112">Se viene caricata un'immagine, ma alcuni la compilazione JIT deve essere eseguita per quell'immagine (che sarà il caso se l'immagine contiene generics), il flag del compilatore specificato da di `SetDesiredNGENCompilerFlags` metodo verrà applicate a compilazione JIT aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="65290-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="65290-113">Il `SetDesiredNGENCompilerFlags` metodo deve essere chiamato durante il [ICorDebugManagedCallback::](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span><span class="sxs-lookup"><span data-stu-id="65290-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="65290-114">Tenta di chiamare il `SetDesiredNGENCompilerFlags` metodo in un secondo momento avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="65290-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="65290-115">Inoltre, i tentativi di impostare i flag che non sono definite nel `CorDebugJITCompilerFlags` enumerazione o che non sono consentiti per il processo specificato non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="65290-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65290-116">Requisiti</span><span class="sxs-lookup"><span data-stu-id="65290-116">Requirements</span></span>  
 <span data-ttu-id="65290-117">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65290-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65290-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="65290-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="65290-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65290-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65290-120">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65290-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65290-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="65290-121">See also</span></span>
- [<span data-ttu-id="65290-122">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="65290-122">ICorDebug Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [<span data-ttu-id="65290-123">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="65290-123">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
