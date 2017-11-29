---
title: Metodo ICorDebugProcess::GetHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess.GetHandle
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess::GetHandle
helpviewer_keywords:
- GetHandle method, ICorDebugProcess interface [.NET Framework debugging]
- ICorDebugProcess::GetHandle method [.NET Framework debugging]
ms.assetid: e7d3ecf5-09d2-4d94-abb6-ff3483deebb6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 139d9341e11b87aa0c10146fdfeaa3752e32467b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugprocessgethandle-method"></a><span data-ttu-id="c0720-102">Metodo ICorDebugProcess::GetHandle</span><span class="sxs-lookup"><span data-stu-id="c0720-102">ICorDebugProcess::GetHandle Method</span></span>
<span data-ttu-id="c0720-103">Ottiene un handle per il processo.</span><span class="sxs-lookup"><span data-stu-id="c0720-103">Gets a handle to the process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c0720-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c0720-104">Syntax</span></span>  
  
```  
HRESULT GetHandle([out] HPROCESS *phProcessHandle);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c0720-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c0720-105">Parameters</span></span>  
 `phProcessHandle`  
 <span data-ttu-id="c0720-106">[out] Un puntatore a un `HPROCESS` che rappresenta l'handle del processo.</span><span class="sxs-lookup"><span data-stu-id="c0720-106">[out] A pointer to an `HPROCESS` that is the handle to the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c0720-107">Note</span><span class="sxs-lookup"><span data-stu-id="c0720-107">Remarks</span></span>  
 <span data-ttu-id="c0720-108">L'handle recuperato è di proprietà dell'interfaccia di debug.</span><span class="sxs-lookup"><span data-stu-id="c0720-108">The retrieved handle is owned by the debugging interface.</span></span> <span data-ttu-id="c0720-109">Il debugger deve duplicare l'handle prima di utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="c0720-109">The debugger should duplicate the handle before using it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c0720-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c0720-110">Requirements</span></span>  
 <span data-ttu-id="c0720-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0720-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0720-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c0720-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c0720-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c0720-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c0720-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0720-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
