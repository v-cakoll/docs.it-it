---
title: Metodo ICorDebugModule2::SetJITCompilerFlags
ms.date: 03/30/2017
api_name:
- ICorDebugModule2.SetJITCompilerFlags
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type:
- apiref
ms.openlocfilehash: 2358cee1b3a9aa50fb1f0e61d558f164a39aa86c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137354"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="1b745-102">Metodo ICorDebugModule2::SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="1b745-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="1b745-103">Imposta i flag che controllano la compilazione JIT (just-in-Time) di questo ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="1b745-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b745-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="1b745-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1b745-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="1b745-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="1b745-106">in Combinazione bit per bit dei valori dell'enumerazione [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="1b745-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b745-107">Note</span><span class="sxs-lookup"><span data-stu-id="1b745-107">Remarks</span></span>  
 <span data-ttu-id="1b745-108">Se il valore `dwFlags` non è valido, il `SetJITCompilerFlags` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1b745-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="1b745-109">Il metodo `SetJITCompilerFlags` può essere chiamato solo dall'interno del callback [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="1b745-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="1b745-110">Il tentativo di chiamare questo oggetto dopo il recapito `ICorDebugManagedCallback::LoadModule` callback avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1b745-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="1b745-111">La funzionalità modifica e continuazione non è supportata nelle piattaforme Win9x o a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="1b745-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="1b745-112">Se pertanto si chiama il metodo `SetJITCompilerFlags` su una di queste due piattaforme con il flag CORDEBUG_JIT_ENABLE_ENC impostato in `dwFlags`, il metodo `SetJITCompilerFlags` e tutti i metodi specifici per la modifica e la continuazione, ad esempio [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="1b745-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1b745-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="1b745-113">Requirements</span></span>  
 <span data-ttu-id="1b745-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b745-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b745-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="1b745-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="1b745-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1b745-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1b745-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b745-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
