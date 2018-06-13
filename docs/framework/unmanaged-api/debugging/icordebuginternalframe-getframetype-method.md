---
title: Metodo ICorDebugInternalFrame::GetFrameType
ms.date: 03/30/2017
api_name:
- ICorDebugInternalFrame.GetFrameType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugInternalFrame::GetFrameType
helpviewer_keywords:
- GetFrameType method [.NET Framework debugging]
- ICorDebugInternalFrame::GetFrameType method [.NET Framework debugging]
ms.assetid: da278a29-dc2e-4bf7-96ce-801bdc4d7025
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f7e5fceacc3fefa9267a9d7f989e745c392322e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33414125"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="b4428-102">Metodo ICorDebugInternalFrame::GetFrameType</span><span class="sxs-lookup"><span data-stu-id="b4428-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="b4428-103">Ottiene il tipo di questo frame interno.</span><span class="sxs-lookup"><span data-stu-id="b4428-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4428-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b4428-104">Syntax</span></span>  
  
```  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b4428-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b4428-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="b4428-106">[out] Un puntatore a un valore di enumerazione CorDebugInternalFrameType che indica il tipo di frame interni, rappresentato da questo `ICorDebugInternalFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="b4428-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4428-107">Note</span><span class="sxs-lookup"><span data-stu-id="b4428-107">Remarks</span></span>  
 <span data-ttu-id="b4428-108">Il tipo di frame interni non sarà mai STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="b4428-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="b4428-109">Debugger devono normalmente ignorare i tipi di frame interni non riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="b4428-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4428-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b4428-110">Requirements</span></span>  
 <span data-ttu-id="b4428-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4428-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4428-112">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b4428-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4428-113">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="b4428-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4428-114">**Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4428-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
