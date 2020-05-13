---
title: Metodo ICorDebugModule::IsDynamic
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsDynamic
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsDynamic
helpviewer_keywords:
- IsDynamic method [.NET Framework debugging]
- ICorDebugModule::IsDynamic method [.NET Framework debugging]
ms.assetid: 5eefe716-5025-4a4c-970c-c823cdc7bb87
topic_type:
- apiref
ms.openlocfilehash: 4517f266bbb500223214a6a8fe5881e8b29566c3
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206891"
---
# <a name="icordebugmoduleisdynamic-method"></a><span data-ttu-id="ef51f-102">Metodo ICorDebugModule::IsDynamic</span><span class="sxs-lookup"><span data-stu-id="ef51f-102">ICorDebugModule::IsDynamic Method</span></span>
<span data-ttu-id="ef51f-103">Ottiene un valore che indica se il modulo è dinamico.</span><span class="sxs-lookup"><span data-stu-id="ef51f-103">Gets a value that indicates whether this module is dynamic.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef51f-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ef51f-104">Syntax</span></span>  
  
```cpp  
HRESULT IsDynamic(  
    [out] BOOL *pDynamic  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef51f-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ef51f-105">Parameters</span></span>  
 `pDynamic`  
 <span data-ttu-id="ef51f-106">[out] `true` Se il modulo è dinamico; in caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="ef51f-106">[out] `true` if this module is dynamic; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ef51f-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="ef51f-107">Remarks</span></span>  
 <span data-ttu-id="ef51f-108">Un modulo dinamico può aggiungere nuove classi ed eliminare le classi esistenti anche dopo il caricamento del modulo.</span><span class="sxs-lookup"><span data-stu-id="ef51f-108">A dynamic module can add new classes and delete existing classes even after the module has been loaded.</span></span> <span data-ttu-id="ef51f-109">I callback [ICorDebugManagedCallback:: LoadClass](icordebugmanagedcallback-loadclass-method.md) e [ICorDebugManagedCallback:: UnloadClass](icordebugmanagedcallback-unloadclass-method.md) indicano al debugger quando una classe è stata aggiunta o eliminata.</span><span class="sxs-lookup"><span data-stu-id="ef51f-109">The [ICorDebugManagedCallback::LoadClass](icordebugmanagedcallback-loadclass-method.md) and [ICorDebugManagedCallback::UnloadClass](icordebugmanagedcallback-unloadclass-method.md) callbacks inform the debugger when a class has been added or deleted.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef51f-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ef51f-110">Requirements</span></span>  
 <span data-ttu-id="ef51f-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef51f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef51f-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ef51f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ef51f-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef51f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef51f-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef51f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
