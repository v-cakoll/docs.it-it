---
title: Metodo ICorDebugModule2::SetJITCompilerFlags
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModule2.SetJITCompilerFlags
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModule2::SetJITCompilerFlags
helpviewer_keywords:
- ICorDebugModule2::SetJITCompilerFlags method [.NET Framework debugging]
- SetJITCompilerFlags method [.NET Framework debugging]
ms.assetid: ea574c84-c622-4589-9a14-b55771af5e06
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: cfc25e9ce15996360cd0e3c68805d3707b325f79
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="31d11-102">Metodo ICorDebugModule2::SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="31d11-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="31d11-103">Imposta i flag che controllano la compilazione just-in-time (JIT) di questa interfaccia ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="31d11-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d11-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="31d11-104">Syntax</span></span>  
  
```  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="31d11-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="31d11-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="31d11-106">[in] Combinazione bit per bit di [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) valori di enumerazione.</span><span class="sxs-lookup"><span data-stu-id="31d11-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](../../../../docs/framework/unmanaged-api/debugging/cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31d11-107">Note</span><span class="sxs-lookup"><span data-stu-id="31d11-107">Remarks</span></span>  
 <span data-ttu-id="31d11-108">Se il `dwFlags` valore non è valido, il `SetJITCompilerFlags` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="31d11-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="31d11-109">Il `SetJITCompilerFlags` metodo può essere chiamato solo dall'interno di [ICorDebugManagedCallback:: LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="31d11-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="31d11-110">Tenta di chiamare dopo il `ICorDebugManagedCallback::LoadModule` callback è stato inviato avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="31d11-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="31d11-111">Modifica e continuazione non è supportata in 64 bit o in piattaforme Win9x.</span><span class="sxs-lookup"><span data-stu-id="31d11-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="31d11-112">Pertanto, se si chiama il `SetJITCompilerFlags` metodo su una di queste due piattaforme con il flag CORDEBUG_JIT_ENABLE_ENC impostato `dwFlags`, `SetJITCompilerFlags` (metodo) e tutti i metodi specifici di modifica e continuazione, ad esempio [ICorDebugModule2:: ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="31d11-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](../../../../docs/framework/unmanaged-api/debugging/icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d11-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="31d11-113">Requirements</span></span>  
 <span data-ttu-id="31d11-114">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31d11-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d11-115">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="31d11-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="31d11-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31d11-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="31d11-117">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d11-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
