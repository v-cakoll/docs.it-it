---
title: Metodo ICorDebugThread::GetHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c7a932d04fef438e19176af565c92e0673339e02
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadgethandle-method"></a><span data-ttu-id="7b783-102">Metodo ICorDebugThread::GetHandle</span><span class="sxs-lookup"><span data-stu-id="7b783-102">ICorDebugThread::GetHandle Method</span></span>
<span data-ttu-id="7b783-103">Ottiene l'handle corrente per la parte attiva del ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="7b783-103">Gets the current handle for the active part of this ICorDebugThread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b783-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7b783-104">Syntax</span></span>  
  
```  
HRESULT GetHandle (  
    [out] HTHREAD *phThreadHandle  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7b783-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7b783-105">Parameters</span></span>  
 `phThreadHandle`  
 <span data-ttu-id="7b783-106">[out] Un puntatore a un HTHREAD che rappresenta l'handle della parte attiva del thread.</span><span class="sxs-lookup"><span data-stu-id="7b783-106">[out] A pointer to an HTHREAD that is the handle of the active part of this thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7b783-107">Note</span><span class="sxs-lookup"><span data-stu-id="7b783-107">Remarks</span></span>  
 <span data-ttu-id="7b783-108">L'handle può cambiare durante il processo viene eseguito e può essere diverso per le diverse parti del thread.</span><span class="sxs-lookup"><span data-stu-id="7b783-108">The handle may change as the process executes, and may be different for different parts of the thread.</span></span>  
  
 <span data-ttu-id="7b783-109">Questo handle è di proprietà dell'API di debug.</span><span class="sxs-lookup"><span data-stu-id="7b783-109">This handle is owned by the debugging API.</span></span> <span data-ttu-id="7b783-110">Il debugger deve duplicarlo prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="7b783-110">The debugger should duplicate it before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7b783-111">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7b783-111">Requirements</span></span>  
 <span data-ttu-id="7b783-112">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7b783-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7b783-113">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="7b783-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7b783-114">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7b783-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7b783-115">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7b783-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
