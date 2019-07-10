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
ms.openlocfilehash: 2a5461cc6a78347cdbe0d0b13f8111cb24c11006
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760051"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="9df1e-102">Metodo ICorDebugInternalFrame::GetFrameType</span><span class="sxs-lookup"><span data-stu-id="9df1e-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="9df1e-103">Ottiene il tipo di questo frame interno.</span><span class="sxs-lookup"><span data-stu-id="9df1e-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9df1e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="9df1e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9df1e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="9df1e-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="9df1e-106">[out] Un puntatore a un valore dell'enumerazione che indica il tipo di frame interno rappresentato da questo CorDebugInternalFrameType `ICorDebugInternalFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="9df1e-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9df1e-107">Note</span><span class="sxs-lookup"><span data-stu-id="9df1e-107">Remarks</span></span>  
 <span data-ttu-id="9df1e-108">Il tipo di frame interno non sarà mai STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="9df1e-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="9df1e-109">I debugger normalmente devono ignorare i tipi di frame interno non riconosciuto.</span><span class="sxs-lookup"><span data-stu-id="9df1e-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9df1e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="9df1e-110">Requirements</span></span>  
 <span data-ttu-id="9df1e-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9df1e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9df1e-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9df1e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9df1e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9df1e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9df1e-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9df1e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
