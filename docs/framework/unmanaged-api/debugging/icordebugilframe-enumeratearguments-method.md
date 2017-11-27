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
ms.openlocfilehash: bf345f3fa684b57a33e3452916535b1cd7db3c8b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugilframeenumeratearguments-method"></a><span data-ttu-id="3ef6c-102">Metodo ICorDebugILFrame::EnumerateArguments</span><span class="sxs-lookup"><span data-stu-id="3ef6c-102">ICorDebugILFrame::EnumerateArguments Method</span></span>
<span data-ttu-id="3ef6c-103">Ottiene un enumeratore per gli argomenti nel frame.</span><span class="sxs-lookup"><span data-stu-id="3ef6c-103">Gets an enumerator for the arguments in this frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3ef6c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3ef6c-104">Syntax</span></span>  
  
```  
HRESULT EnumerateArguments (  
    [out] ICorDebugValueEnum    **ppValueEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3ef6c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3ef6c-105">Parameters</span></span>  
 `ppValueEnum`  
 <span data-ttu-id="3ef6c-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugValueEnum che è l'enumeratore per gli argomenti nel frame.</span><span class="sxs-lookup"><span data-stu-id="3ef6c-106">[out] A pointer to the address of an ICorDebugValueEnum object that is the enumerator for the arguments in this frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3ef6c-107">Note</span><span class="sxs-lookup"><span data-stu-id="3ef6c-107">Remarks</span></span>  
 <span data-ttu-id="3ef6c-108">`EnumerateArguments`Ottiene un enumeratore in grado di elencare gli argomenti disponibili nel frame di chiamata che è rappresentato dall'oggetto ICorDebugILFrame.</span><span class="sxs-lookup"><span data-stu-id="3ef6c-108">`EnumerateArguments` gets an enumerator that can list the arguments available in the call frame that is represented by this ICorDebugILFrame object.</span></span> <span data-ttu-id="3ef6c-109">L'elenco includerà gli argomenti devono essere [vararg](/cpp/windows/vararg) (ovvero, un numero variabile di argomenti) e argomenti che non sono `vararg`.</span><span class="sxs-lookup"><span data-stu-id="3ef6c-109">The list will include arguments that are [vararg](/cpp/windows/vararg) (that is, a variable number of arguments) as well as arguments that are not `vararg`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3ef6c-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3ef6c-110">Requirements</span></span>  
 <span data-ttu-id="3ef6c-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ef6c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ef6c-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="3ef6c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3ef6c-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3ef6c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3ef6c-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3ef6c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
