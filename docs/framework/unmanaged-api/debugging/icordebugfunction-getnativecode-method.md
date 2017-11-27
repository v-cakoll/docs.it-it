---
title: Metodo ICorDebugFunction::GetNativeCode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugFunction.GetNativeCode
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugFunction::GetNativeCode
helpviewer_keywords:
- GetNativeCode method [.NET Framework debugging]
- ICorDebugFunction::GetNativeCode method [.NET Framework debugging]
ms.assetid: c8a34916-0eef-4987-8d29-c8bcb4be9cf6
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2fccfaeb346d59f5cf565f47a9a64e732706adad
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugfunctiongetnativecode-method"></a><span data-ttu-id="b24db-102">Metodo ICorDebugFunction::GetNativeCode</span><span class="sxs-lookup"><span data-stu-id="b24db-102">ICorDebugFunction::GetNativeCode Method</span></span>
<span data-ttu-id="b24db-103">Ottiene il codice nativo per la funzione che è rappresentata da questa istanza di ICorDebugFunction.</span><span class="sxs-lookup"><span data-stu-id="b24db-103">Gets the native code for the function that is represented by this ICorDebugFunction instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b24db-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b24db-104">Syntax</span></span>  
  
```  
HRESULT GetNativeCode (  
    [out] ICorDebugCode **ppCode  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b24db-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b24db-105">Parameters</span></span>  
 `ppCode`  
 <span data-ttu-id="b24db-106">[out] Un puntatore all'istanza di ICorDebugCode che rappresenta il codice nativo per questa funzione, o null, se questa funzione è codice Microsoft intermediate language (MSIL) che non è stato just-in-time (JIT) compilati.</span><span class="sxs-lookup"><span data-stu-id="b24db-106">[out] A pointer to the ICorDebugCode instance that represents the native code for this function, or null, if this function is Microsoft intermediate language (MSIL) code that has not been just-in-time (JIT) compiled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b24db-107">Note</span><span class="sxs-lookup"><span data-stu-id="b24db-107">Remarks</span></span>  
 <span data-ttu-id="b24db-108">Se la funzione che è rappresentata da questo `ICorDebugFunction` istanza è stata compilata tramite JIT più volte, come nel caso di tipi generici, `GetNativeCode` restituisce un oggetto di codice nativo casuale.</span><span class="sxs-lookup"><span data-stu-id="b24db-108">If the function that is represented by this `ICorDebugFunction` instance has been JIT-compiled more than once, as in the case of generic types, `GetNativeCode` returns a random native code object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b24db-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b24db-109">Requirements</span></span>  
 <span data-ttu-id="b24db-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b24db-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b24db-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="b24db-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b24db-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b24db-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b24db-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b24db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
