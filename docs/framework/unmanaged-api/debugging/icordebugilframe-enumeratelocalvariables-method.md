---
title: Metodo ICorDebugILFrame::EnumerateLocalVariables
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateLocalVariables
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateLocalVariables
helpviewer_keywords:
- EnumerateLocalVariables method [.NET Framework debugging]
- ICorDebugILFrame::EnumerateLocalVariables method [.NET Framework debugging]
ms.assetid: 1a67fa1b-2419-4cd0-aad4-6f46a0719b4b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb4e6bead1bb4933f8f9af4ffb1bfb9157a028c7
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframeenumeratelocalvariables-method"></a><span data-ttu-id="e706d-102">Metodo ICorDebugILFrame::EnumerateLocalVariables</span><span class="sxs-lookup"><span data-stu-id="e706d-102">ICorDebugILFrame::EnumerateLocalVariables Method</span></span>
<span data-ttu-id="e706d-103">Ottiene un enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="e706d-103">Gets an enumerator for the local variables in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e706d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e706d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateLocalVariables(   
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e706d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="e706d-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="e706d-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per le variabili locali nel frame.</span><span class="sxs-lookup"><span data-stu-id="e706d-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the local variables in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e706d-107">Note</span><span class="sxs-lookup"><span data-stu-id="e706d-107">Remarks</span></span>  
 <span data-ttu-id="e706d-108">`EnumerateLocalVariables`Ottiene un enumeratore in grado di elencare le variabili locali disponibili nel frame di chiamata che è rappresentato dall'oggetto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="e706d-108">`EnumerateLocalVariables` gets an enumerator that can list the local variables available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="e706d-109">L'elenco potrebbe non includere tutte le variabili locali nella funzione in esecuzione, perché alcuni dei quali potrebbero non essere attivo.</span><span class="sxs-lookup"><span data-stu-id="e706d-109">The list may not include all of the local variables in the running function, because some of them may not be active.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e706d-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="e706d-110">Requirements</span></span>  
 <span data-ttu-id="e706d-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e706d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e706d-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="e706d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e706d-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e706d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e706d-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e706d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
