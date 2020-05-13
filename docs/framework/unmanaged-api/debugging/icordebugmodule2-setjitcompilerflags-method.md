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
ms.openlocfilehash: f73919634ba15dfd16694676d1389875fc2d79bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210189"
---
# <a name="icordebugmodule2setjitcompilerflags-method"></a><span data-ttu-id="3eadb-102">Metodo ICorDebugModule2::SetJITCompilerFlags</span><span class="sxs-lookup"><span data-stu-id="3eadb-102">ICorDebugModule2::SetJITCompilerFlags Method</span></span>
<span data-ttu-id="3eadb-103">Imposta i flag che controllano la compilazione JIT (just-in-Time) di questo ICorDebugModule2.</span><span class="sxs-lookup"><span data-stu-id="3eadb-103">Sets the flags that control the just-in-time (JIT) compilation of this ICorDebugModule2.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3eadb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3eadb-104">Syntax</span></span>  
  
```cpp  
HRESULT SetJITCompilerFlags (  
    [in] DWORD dwFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3eadb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3eadb-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="3eadb-106">in Combinazione bit per bit dei valori dell'enumerazione [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="3eadb-106">[in] A bitwise combination of the [CorDebugJITCompilerFlags](cordebugjitcompilerflags-enumeration.md) enumeration values.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3eadb-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="3eadb-107">Remarks</span></span>  
 <span data-ttu-id="3eadb-108">Se il `dwFlags` valore non è valido, il `SetJITCompilerFlags` metodo avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3eadb-108">If the `dwFlags` value is invalid, the `SetJITCompilerFlags` method will fail.</span></span>  
  
 <span data-ttu-id="3eadb-109">Il `SetJITCompilerFlags` metodo può essere chiamato solo dall'interno del callback [ICorDebugManagedCallback:: LoadModule](icordebugmanagedcallback-loadmodule-method.md) per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="3eadb-109">The `SetJITCompilerFlags` method can be called only from within the [ICorDebugManagedCallback::LoadModule](icordebugmanagedcallback-loadmodule-method.md) callback for this module.</span></span> <span data-ttu-id="3eadb-110">Il tentativo di chiamare questo oggetto dopo il recapito del `ICorDebugManagedCallback::LoadModule` callback avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3eadb-110">Attempts to call it after the `ICorDebugManagedCallback::LoadModule` callback has been delivered will fail.</span></span>  
  
 <span data-ttu-id="3eadb-111">La funzionalità modifica e continuazione non è supportata nelle piattaforme Win9x o a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="3eadb-111">Edit and Continue is not supported on 64-bit or Win9x platforms.</span></span> <span data-ttu-id="3eadb-112">Se pertanto si chiama il `SetJITCompilerFlags` metodo su una di queste due piattaforme con il flag di CORDEBUG_JIT_ENABLE_ENC impostato in `dwFlags` , il `SetJITCompilerFlags` metodo e tutti i metodi specifici per la modifica e la continuazione, ad esempio [ICorDebugModule2:: ApplyChanges](icordebugmodule2-applychanges-method.md), avranno esito negativo.</span><span class="sxs-lookup"><span data-stu-id="3eadb-112">Therefore, if you call the `SetJITCompilerFlags` method on either of these two platforms with the CORDEBUG_JIT_ENABLE_ENC flag set in `dwFlags`, the `SetJITCompilerFlags` method and all methods specific to Edit and Continue, such as [ICorDebugModule2::ApplyChanges](icordebugmodule2-applychanges-method.md), will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3eadb-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3eadb-113">Requirements</span></span>  
 <span data-ttu-id="3eadb-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3eadb-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3eadb-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3eadb-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3eadb-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3eadb-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3eadb-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3eadb-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
