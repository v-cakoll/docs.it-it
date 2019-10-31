---
title: 'Metodo IcorDebugVariableHome:: GetLiveRange'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetLiveRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetLiveRange
helpviewer_keywords:
- ICorDebugVariableHome::GetLiveRange method [.NET Framework debugging]
- GetLiveRange method, ICorDebugVariableFrame interface [.NET Framework debugging]
ms.assetid: 87277e1a-1595-4729-9e25-d1c3ac18ce5f
topic_type:
- apiref
ms.openlocfilehash: a8b8955d2f4c164031974f0d9021fb766ff2c030
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125124"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="ac011-102">Metodo IcorDebugVariableHome:: GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="ac011-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="ac011-103">Ottiene l'intervallo nativo su cui questa variabile è attiva.</span><span class="sxs-lookup"><span data-stu-id="ac011-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac011-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ac011-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac011-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ac011-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="ac011-106">out Offset logico in corrispondenza del quale la variabile è la prima Live.</span><span class="sxs-lookup"><span data-stu-id="ac011-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="ac011-107">out Offset logico immediatamente dopo il punto in cui la variabile è l'ultima volta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ac011-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac011-108">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ac011-108">Requirements</span></span>  
 <span data-ttu-id="ac011-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac011-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac011-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ac011-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ac011-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ac011-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ac011-112">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac011-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac011-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ac011-113">See also</span></span>

- [<span data-ttu-id="ac011-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="ac011-114">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
