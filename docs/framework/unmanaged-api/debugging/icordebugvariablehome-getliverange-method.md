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
ms.openlocfilehash: 28e41106ffcaf1ed2ed87166e641bb5e5f447e47
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791025"
---
# <a name="icordebugvariablehomegetliverange-method"></a><span data-ttu-id="80cfb-102">Metodo IcorDebugVariableHome:: GetLiveRange</span><span class="sxs-lookup"><span data-stu-id="80cfb-102">IcorDebugVariableHome::GetLiveRange Method</span></span>
<span data-ttu-id="80cfb-103">Ottiene l'intervallo nativo su cui questa variabile è attiva.</span><span class="sxs-lookup"><span data-stu-id="80cfb-103">Gets the native range over which this variable is live.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="80cfb-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="80cfb-104">Syntax</span></span>  
  
```cpp  
HRESULT GetLiveRange(  
    [out] ULONG32* pStartOffset,  
    [out] ULONG32 *pEndOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="80cfb-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="80cfb-105">Parameters</span></span>  
 `pStartOffset`  
 <span data-ttu-id="80cfb-106">out Offset logico in corrispondenza del quale la variabile è la prima Live.</span><span class="sxs-lookup"><span data-stu-id="80cfb-106">[out] The logical offset at which the variable is first live.</span></span>  
  
 `pEndOffset`  
 <span data-ttu-id="80cfb-107">out Offset logico immediatamente dopo il punto in cui la variabile è l'ultima volta in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="80cfb-107">[out] The logical offset immediately after the point at which the variable is last live.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="80cfb-108">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="80cfb-108">Requirements</span></span>  
 <span data-ttu-id="80cfb-109">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80cfb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80cfb-110">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="80cfb-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="80cfb-111">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80cfb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80cfb-112">**Versioni .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80cfb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cfb-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="80cfb-113">See also</span></span>

- [<span data-ttu-id="80cfb-114">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="80cfb-114">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
