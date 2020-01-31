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
ms.openlocfilehash: 9f62d94d30c8c4f23073895b8ff0f7afa2dbad6b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792489"
---
# <a name="icordebugprocess2setdesiredngencompilerflags-method"></a><span data-ttu-id="5e23e-102">Metodo ICorDebugProcess2::SetDesiredNGENCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="5e23e-102">ICorDebugProcess2::SetDesiredNGENCompilerFlags Method</span></span>
<span data-ttu-id="5e23e-103">Imposta i flag che devono essere incorporati in un'immagine precompilata per consentire al runtime di caricare tale immagine nel processo corrente.</span><span class="sxs-lookup"><span data-stu-id="5e23e-103">Sets the flags that must be embedded in a precompiled image in order for the runtime to load that image into the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e23e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e23e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDesiredNGENCompilerFlags (  
    [in] DWORD    pdwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e23e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e23e-105">Parameters</span></span>  
 `pdwFlags`  
 <span data-ttu-id="5e23e-106">in Valore dell'enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) che specifica i flag del compilatore usati per selezionare l'immagine precompilata corretta.</span><span class="sxs-lookup"><span data-stu-id="5e23e-106">[in] A value of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration that specifies the compiler flags used to select the correct pre-compiled image.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e23e-107">Note</span><span class="sxs-lookup"><span data-stu-id="5e23e-107">Remarks</span></span>  
 <span data-ttu-id="5e23e-108">Il metodo `SetDesiredNGENCompilerFlags` specifica i flag che devono essere incorporati in un'immagine precompilata in modo che il runtime caricherà tale immagine in questo processo.</span><span class="sxs-lookup"><span data-stu-id="5e23e-108">The `SetDesiredNGENCompilerFlags` method specifies the flags that must be embedded in a precompiled image so that the runtime will load that image into this process.</span></span> <span data-ttu-id="5e23e-109">I flag impostati da questo metodo vengono utilizzati solo per selezionare l'immagine precompilata corretta.</span><span class="sxs-lookup"><span data-stu-id="5e23e-109">The flags set by this method are used only to select the correct precompiled image.</span></span> <span data-ttu-id="5e23e-110">Se tale immagine non esiste, il runtime caricherà l'immagine Microsoft Intermediate Language (MSIL) e il compilatore just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="5e23e-110">If no such image exists, the runtime will load the Microsoft intermediate language (MSIL) image and the just-in-time (JIT) compiler instead.</span></span> <span data-ttu-id="5e23e-111">In tal caso, il debugger deve continuare a usare il metodo [ICorDebugModule2:: SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) per impostare i flag come desiderato per la compilazione JIT.</span><span class="sxs-lookup"><span data-stu-id="5e23e-111">In that case, the debugger must still use the [ICorDebugModule2::SetJITCompilerFlags](icordebugmodule2-setjitcompilerflags-method.md) method to set the flags as desired for the JIT compilation.</span></span>  
  
 <span data-ttu-id="5e23e-112">Se viene caricata un'immagine, ma è necessario che venga eseguita una compilazione JIT per tale immagine, come avviene nel caso in cui l'immagine contenga generics, i flag del compilatore specificati dal metodo `SetDesiredNGENCompilerFlags` verranno applicati alla compilazione JIT aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="5e23e-112">If an image is loaded, but some JIT compiling must take place for that image (which will be the case if the image contains generics), the compiler flags specified by the `SetDesiredNGENCompilerFlags` method will apply to the extra JIT compilation.</span></span>  
  
 <span data-ttu-id="5e23e-113">Il metodo di `SetDesiredNGENCompilerFlags` deve essere chiamato durante il callback [ICorDebugManagedCallback:: CreateProcess](icordebugmanagedcallback-createprocess-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5e23e-113">The `SetDesiredNGENCompilerFlags` method must be called during the [ICorDebugManagedCallback::CreateProcess](icordebugmanagedcallback-createprocess-method.md) callback.</span></span> <span data-ttu-id="5e23e-114">I tentativi di chiamare il metodo `SetDesiredNGENCompilerFlags` in un secondo momento avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e23e-114">Attempts to call the `SetDesiredNGENCompilerFlags` method afterwards will fail.</span></span> <span data-ttu-id="5e23e-115">Inoltre, i tentativi di impostare flag che non sono definiti nell'enumerazione `CorDebugJITCompilerFlags` o non sono validi per il processo specificato avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="5e23e-115">Also, attempts to set flags that are either not defined in the `CorDebugJITCompilerFlags` enumeration or are not legal for the given process will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e23e-116">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="5e23e-116">Requirements</span></span>  
 <span data-ttu-id="5e23e-117">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e23e-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e23e-118">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e23e-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e23e-119">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e23e-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e23e-120">**Versioni .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e23e-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e23e-121">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e23e-121">See also</span></span>

- [<span data-ttu-id="5e23e-122">Interfaccia ICorDebug</span><span class="sxs-lookup"><span data-stu-id="5e23e-122">ICorDebug Interface</span></span>](icordebug-interface.md)
- [<span data-ttu-id="5e23e-123">Interfaccia ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5e23e-123">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
