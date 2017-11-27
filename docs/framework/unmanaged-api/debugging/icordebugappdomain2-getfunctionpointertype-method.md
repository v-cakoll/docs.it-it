---
title: Metodo ICorDebugAppDomain2::GetFunctionPointerType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugAppDomain2.GetFunctionPointerType
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugAppDomain2::GetFunctionPointerType
helpviewer_keywords:
- ICorDebugAppDomain2::GetFunctionPointerType method [.NET Framework debugging]
- GetFunctionPointerType method [.NET Framework debugging]
ms.assetid: 0aba6096-5b38-435c-a72a-86d35db4daef
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 85c07ec6177621b571a376ad58a386e8ed31ea63
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugappdomain2getfunctionpointertype-method"></a><span data-ttu-id="c950e-102">Metodo ICorDebugAppDomain2::GetFunctionPointerType</span><span class="sxs-lookup"><span data-stu-id="c950e-102">ICorDebugAppDomain2::GetFunctionPointerType Method</span></span>
<span data-ttu-id="c950e-103">Ottiene un puntatore a una funzione che dispone di una determinata firma.</span><span class="sxs-lookup"><span data-stu-id="c950e-103">Gets a pointer to a function that has a given signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c950e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c950e-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionPointerType (  
    [in] ULONG32                             nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType   *ppTypeArgs[],  
    [out] ICorDebugType                      **ppType  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c950e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="c950e-105">Parameters</span></span>  
 `nTypeArgs`  
 <span data-ttu-id="c950e-106">[in] Il numero di argomenti di tipo per la funzione.</span><span class="sxs-lookup"><span data-stu-id="c950e-106">[in] The number of type arguments for the function.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="c950e-107">[in] Matrice di puntatori, ognuno dei quali punta a un oggetto ICorDebugType che rappresenta un argomento di tipo della funzione.</span><span class="sxs-lookup"><span data-stu-id="c950e-107">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument of the function.</span></span> <span data-ttu-id="c950e-108">Il primo elemento è il tipo restituito. tutti gli altri elementi è un tipo di parametro.</span><span class="sxs-lookup"><span data-stu-id="c950e-108">The first element is the return type; each of the other elements is a parameter type.</span></span>  
  
 `ppType`  
 <span data-ttu-id="c950e-109">[out] Un puntatore all'indirizzo di un `ICorDebugType` oggetto che rappresenta il puntatore alla funzione.</span><span class="sxs-lookup"><span data-stu-id="c950e-109">[out] A pointer to the address of an `ICorDebugType` object that represents the pointer to the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c950e-110">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c950e-110">Requirements</span></span>  
 <span data-ttu-id="c950e-111">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c950e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c950e-112">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="c950e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c950e-113">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c950e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c950e-114">**Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c950e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
