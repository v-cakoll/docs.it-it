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
ms.openlocfilehash: b7a33fd6e2178e0e9188b81f516b231702fb6460
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122719"
---
# <a name="icordebuginternalframegetframetype-method"></a><span data-ttu-id="502df-102">Metodo ICorDebugInternalFrame::GetFrameType</span><span class="sxs-lookup"><span data-stu-id="502df-102">ICorDebugInternalFrame::GetFrameType Method</span></span>
<span data-ttu-id="502df-103">Ottiene il tipo del frame interno.</span><span class="sxs-lookup"><span data-stu-id="502df-103">Gets the type of this internal frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="502df-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="502df-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFrameType (  
    [out] CorDebugInternalFrameType  *pType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="502df-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="502df-105">Parameters</span></span>  
 `pType`  
 <span data-ttu-id="502df-106">out Puntatore a un valore dell'enumerazione CorDebugInternalFrameType che indica il tipo di frame interno rappresentato da questo oggetto `ICorDebugInternalFrame`.</span><span class="sxs-lookup"><span data-stu-id="502df-106">[out] A pointer to a value of the CorDebugInternalFrameType enumeration that indicates the type of internal frame represented by this `ICorDebugInternalFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="502df-107">Note</span><span class="sxs-lookup"><span data-stu-id="502df-107">Remarks</span></span>  
 <span data-ttu-id="502df-108">Il tipo di frame interno non sarà mai STUBFRAME_NONE.</span><span class="sxs-lookup"><span data-stu-id="502df-108">The internal frame type will never be STUBFRAME_NONE.</span></span> <span data-ttu-id="502df-109">I debugger devono ignorare normalmente i tipi di frame interni non riconosciuti.</span><span class="sxs-lookup"><span data-stu-id="502df-109">Debuggers should gracefully ignore unrecognized internal frame types.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="502df-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="502df-110">Requirements</span></span>  
 <span data-ttu-id="502df-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="502df-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="502df-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="502df-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="502df-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="502df-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="502df-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="502df-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
