---
title: Metodo ICorDebugInternalFrame::GetFrameType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugInternalFrame.GetFrameType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9d3dd087662c938b2f733458d1e92cff577e9f7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="55a67-102">Metodo ICorDebugInternalFrame::GetFrameType</span><span class="sxs-lookup"><span data-stu-id="55a67-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="55a67-103">Ottiene il tipo di questo frame interno.</span><span class="sxs-lookup"><span data-stu-id="55a67-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55a67-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="55a67-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="55a67-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="55a67-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="55a67-106">[out] Un puntatore a un valore di enumerazione CorDebugInternalFrameType che indica il tipo di frame interni, rappresentato da questo `ICorDebugInternalFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="55a67-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="55a67-107">Note</span><span class="sxs-lookup"><span data-stu-id="55a67-107">Remarks</span></span>  
 <span data-ttu-id="55a67-108">Il tipo di frame interni non sarà mai STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="55a67-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="55a67-109">Debugger devono normalmente ignorare i tipi di frame interni non riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="55a67-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55a67-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="55a67-110">Requirements</span></span>  
 <span data-ttu-id="55a67-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55a67-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55a67-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="55a67-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="55a67-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="55a67-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="55a67-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="55a67-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
