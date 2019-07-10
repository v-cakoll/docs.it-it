---
title: Metodo ICorDebugILFrame::EnumerateArguments
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.EnumerateArguments
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 499f58cc0a3f2d1b3c159435ed7d9b523f25e29e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757898"
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="7ceb4-102">Metodo ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="7ceb4-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="7ceb4-103">Ottiene un enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="7ceb4-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ceb4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="7ceb4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ceb4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="7ceb4-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="7ceb4-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per gli argomenti in questo frame.</span><span class="sxs-lookup"><span data-stu-id="7ceb4-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7ceb4-107">Note</span><span class="sxs-lookup"><span data-stu-id="7ceb4-107">Remarks</span></span>  
 <span data-ttu-id="7ceb4-108">`EnumerateArguments` Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata che è rappresentato da questo ICorDebugILFrame oggetto.</span><span class="sxs-lookup"><span data-stu-id="7ceb4-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="7ceb4-109">L'elenco includerà gli argomenti [vararg](/cpp/windows/vararg) (vale a dire, un numero variabile di argomenti), nonché di argomenti non `vararg`.</span><span class="sxs-lookup"><span data-stu-id="7ceb4-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ceb4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="7ceb4-110">Requirements</span></span>  
 <span data-ttu-id="7ceb4-111">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ceb4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ceb4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ceb4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ceb4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ceb4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ceb4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ceb4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
