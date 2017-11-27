---
title: Metodo ICorDebugThread::GetHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread.GetHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugThread interface [.NET Framework debugging]
- ICorDebugThread::GetHandle method [.NET Framework debugging]
ms.assetid: 172ef8c4-2ead-4cfc-bd2e-dee4fb7191cd
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3cd5f7191c00b7c6b07bacc463d906982c994578
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="e17a7-102">Metodo ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="e17a7-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="e17a7-103">Ottiene l'handle corrente per la parte attiva del ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="e17a7-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e17a7-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e17a7-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e17a7-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e17a7-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="e17a7-106">[out] Un puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.</span><span class="sxs-lookup"><span data-stu-id="e17a7-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e17a7-107">Note</span><span class="sxs-lookup"><span data-stu-id="e17a7-107">Remarks</span></span>  
 <span data-ttu-id="e17a7-108">L'handle può cambiare durante il processo viene eseguito e può essere diverso per le diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="e17a7-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="e17a7-109">Questo handle è di proprietà dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="e17a7-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="e17a7-110">Il debugger deve duplicarlo prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="e17a7-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e17a7-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e17a7-111">Requirements</span></span>  
 <span data-ttu-id="e17a7-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e17a7-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e17a7-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e17a7-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e17a7-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e17a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e17a7-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e17a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
