---
title: Metodo ICorDebugILFrame::EnumerateArguments
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugILFrame.EnumerateArguments
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugILFrame::EnumerateArguments
helpviewer_keywords:
- ICorDebugILFrame::EnumerateArguments method [.NET Framework debugging]
- EnumerateArguments method [.NET Framework debugging]
ms.assetid: 00ac81e2-a774-422a-bd88-54a4b3c99f73
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 474118abc505928d16737d792a619e75f1209344
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="a9690-102">Metodo ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="a9690-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="a9690-103">Ottiene un enumeratore per gli argomenti nel frame.</span><span class="sxs-lookup"><span data-stu-id="a9690-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9690-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9690-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a9690-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a9690-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="a9690-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per gli argomenti nel frame.</span><span class="sxs-lookup"><span data-stu-id="a9690-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9690-107">Note</span><span class="sxs-lookup"><span data-stu-id="a9690-107">Remarks</span></span>  
 <span data-ttu-id="a9690-108">`EnumerateArguments`Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata che è rappresentato dall'oggetto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="a9690-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="a9690-109">L'elenco includerà gli argomenti devono essere [vararg](/cpp/windows/vararg) (ovvero, un numero variabile di argomenti) e argomenti che non sono `vararg`.</span><span class="sxs-lookup"><span data-stu-id="a9690-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9690-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a9690-110">Requirements</span></span>  
 <span data-ttu-id="a9690-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9690-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9690-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a9690-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a9690-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9690-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9690-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9690-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
