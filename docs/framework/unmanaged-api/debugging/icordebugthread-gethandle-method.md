---
title: Metodo ICorDebugThread::GetHandle
ms.date: 03/30/2017
api_name:
- ICorDebugThread.GetHandle
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 358597edc9fbc5203e5c00a5fb4d04019281060d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418272"
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="97ddf-102">Metodo ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="97ddf-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="97ddf-103">Ottiene l'handle corrente per la parte attiva del ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="97ddf-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97ddf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="97ddf-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="97ddf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="97ddf-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="97ddf-106">[out] Un puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.</span><span class="sxs-lookup"><span data-stu-id="97ddf-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="97ddf-107">Note</span><span class="sxs-lookup"><span data-stu-id="97ddf-107">Remarks</span></span>  
 <span data-ttu-id="97ddf-108">L'handle può cambiare durante il processo viene eseguito e può essere diverso per le diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="97ddf-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="97ddf-109">Questo handle è di proprietà dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="97ddf-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="97ddf-110">Il debugger deve duplicarlo prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="97ddf-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97ddf-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="97ddf-111">Requirements</span></span>  
 <span data-ttu-id="97ddf-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97ddf-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97ddf-113">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="97ddf-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97ddf-114">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="97ddf-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97ddf-115">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97ddf-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
