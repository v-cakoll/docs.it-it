---
title: Metodo ICorDebugArrayValue::GetDimensions
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugArrayValue.GetDimensions
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugArrayValue::GetDimensions
helpviewer_keywords:
- ICorDebugArrayValue::GetDimensions method [.NET Framework debugging]
- GetDimensions method [.NET Framework debugging]
ms.assetid: 6c116592-134b-4ef2-a319-680e92d013aa
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 364035a0b6e26f5649ef9be5839d096be2fb02dc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugarrayvaluegetdimensions-method"></a><span data-ttu-id="a866e-102">Metodo ICorDebugArrayValue::GetDimensions</span><span class="sxs-lookup"><span data-stu-id="a866e-102">ICorDebugArrayValue::GetDimensions Method</span></span>
<span data-ttu-id="a866e-103">Ottiene il numero di elementi in ogni dimensione di questa matrice.</span><span class="sxs-lookup"><span data-stu-id="a866e-103">Gets the number of elements in each dimension of this array.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a866e-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a866e-104">Syntax</span></span>  
  
```  
HRESULT GetDimensions (  
    [in] ULONG32         cdim,  
    [out, size_is(cdim), length_is(cdim)]   
        ULONG32          dims[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a866e-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="a866e-105">Parameters</span></span>  
 `cdim`  
 <span data-ttu-id="a866e-106">[in] Il numero di dimensioni dell'oggetto ICorDebugArrayValue.</span><span class="sxs-lookup"><span data-stu-id="a866e-106">[in] The number of dimensions of this ICorDebugArrayValue object.</span></span>  
  
 <span data-ttu-id="a866e-107">Questo valore corrisponde anche alla dimensione del `dims` matrice perché la dimensione è uguale al numero di dimensioni del `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="a866e-107">This value is also the size of the `dims` array because its size is equal to the number of dimensions of the `ICorDebugArrayValue` object.</span></span>  
  
 `dims`  
 <span data-ttu-id="a866e-108">[out] Una matrice di interi, ognuno dei quali specifica il numero di elementi in una dimensione in questo `ICorDebugArrayValue` oggetto.</span><span class="sxs-lookup"><span data-stu-id="a866e-108">[out] An array of integers, each of which specifies the number of elements in a dimension in this `ICorDebugArrayValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a866e-109">Requisiti</span><span class="sxs-lookup"><span data-stu-id="a866e-109">Requirements</span></span>  
 <span data-ttu-id="a866e-110">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a866e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a866e-111">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="a866e-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a866e-112">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a866e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a866e-113">**Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a866e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
