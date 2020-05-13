---
title: Metodo ICorDebugILFrame::EnumerateLocalVariables
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateLocalVariables
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type:
- apiref
ms.openlocfilehash: ad1a91e42f582ce96906da5cbf00ca89acb18499
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/12/2020
ms.locfileid: "83210293"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="67860-102">Metodo ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="67860-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="67860-103">Ottiene un enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="67860-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67860-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="67860-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67860-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="67860-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="67860-106">[out] Puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="67860-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="67860-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="67860-107">Remarks</span></span>  
 <span data-ttu-id="67860-108">`EnumerateLocalVariables`Ottiene un enumeratore in grado di elencare le variabili locali disponibili nel frame di chiamata rappresentato da questo oggetto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="67860-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="67860-109">L'elenco potrebbe non includere tutte le variabili locali nella funzione in esecuzione, perché alcune potrebbero non essere attive.</span><span class="sxs-lookup"><span data-stu-id="67860-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67860-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="67860-110">Requirements</span></span>  
 <span data-ttu-id="67860-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67860-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67860-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="67860-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="67860-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67860-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67860-114">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67860-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
