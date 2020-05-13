---
title: Metodo ICorDebugFrame::GetCallee
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetCallee
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetCallee
helpviewer_keywords:
- ICorDebugFrame::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 92d8136d-0436-4c7e-a6b2-80765f892a0d
topic_type:
- apiref
ms.openlocfilehash: 51ac10f936db129282720f2bcae8729f56735b59
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83205374"
---
# <a name="icordebugframegetcallee-method"></a><span data-ttu-id="264ee-102">Metodo ICorDebugFrame::GetCallee</span><span class="sxs-lookup"><span data-stu-id="264ee-102">ICorDebugFrame::GetCallee Method</span></span>
<span data-ttu-id="264ee-103">Ottiene un puntatore all'oggetto ICorDebugFrame nella catena corrente chiamato da questo frame.</span><span class="sxs-lookup"><span data-stu-id="264ee-103">Gets a pointer to the ICorDebugFrame object in the current chain that this frame called.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="264ee-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="264ee-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCallee (  
    [out] ICorDebugFrame     **ppFrame  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="264ee-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="264ee-105">Parameters</span></span>  
 `ppFrame`  
 <span data-ttu-id="264ee-106">out Puntatore all'indirizzo di un `ICorDebugFrame` oggetto che rappresenta il frame chiamato.</span><span class="sxs-lookup"><span data-stu-id="264ee-106">[out] A pointer to the address of an `ICorDebugFrame` object that represents the called frame.</span></span> <span data-ttu-id="264ee-107">Questo valore è null se il frame chiamante è il frame più interno nella catena corrente.</span><span class="sxs-lookup"><span data-stu-id="264ee-107">This value is null if the calling frame is the innermost frame in the current chain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="264ee-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="264ee-108">Requirements</span></span>  
 <span data-ttu-id="264ee-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="264ee-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="264ee-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="264ee-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="264ee-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="264ee-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="264ee-112">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="264ee-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
