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
ms.openlocfilehash: 07331a512dd513a94a7d8c3a8d8b0754d998b94b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131007"
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="f26f4-102">Metodo ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="f26f4-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="f26f4-103">Ottiene un enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="f26f4-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f26f4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f26f4-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f26f4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f26f4-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="f26f4-106">out Puntatore all'indirizzo di un oggetto ICorDebugValueEnum che rappresenta l'enumeratore per le variabili locali in questo frame.</span><span class="sxs-lookup"><span data-stu-id="f26f4-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f26f4-107">Note</span><span class="sxs-lookup"><span data-stu-id="f26f4-107">Remarks</span></span>  
 <span data-ttu-id="f26f4-108">`EnumerateLocalVariables` ottiene un enumeratore in grado di elencare le variabili locali disponibili nel frame di chiamata rappresentato da questo oggetto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="f26f4-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="f26f4-109">L'elenco potrebbe non includere tutte le variabili locali nella funzione in esecuzione, perché alcune potrebbero non essere attive.</span><span class="sxs-lookup"><span data-stu-id="f26f4-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f26f4-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f26f4-110">Requirements</span></span>  
 <span data-ttu-id="f26f4-111">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f26f4-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f26f4-112">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f26f4-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f26f4-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f26f4-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f26f4-114">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f26f4-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
