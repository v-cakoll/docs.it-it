---
title: Metodo ICorDebugArrayValue::HasBaseIndicies
ms.date: 03/30/2017
api_name:
- ICorDebugArrayValue.HasBaseIndicies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugArrayValue::HasBaseIndicies
helpviewer_keywords:
- HasBaseIndicies method [.NET Framework debugging]
- ICorDebugArrayValue::HasBaseIndicies method [.NET Framework debugging]
ms.assetid: aa26df07-e0a6-4608-bdef-d4afafec89aa
topic_type:
- apiref
ms.openlocfilehash: 418ebb51df3f2d86011ee2e77022c3ee5c7ac0b0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73088226"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="235c5-102">Metodo ICorDebugArrayValue::HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="235c5-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="235c5-103">Ottiene un valore che indica se le dimensioni di questa matrice hanno un indice di base di diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="235c5-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="235c5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="235c5-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="235c5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="235c5-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="235c5-106">out Puntatore a un valore booleano che viene `true` se una o più dimensioni di questo oggetto `ICorDebugArrayValue` hanno un indice di base diverso da zero; in caso contrario, il valore booleano viene `false`.</span><span class="sxs-lookup"><span data-stu-id="235c5-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="235c5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="235c5-107">Requirements</span></span>  
 <span data-ttu-id="235c5-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="235c5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="235c5-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="235c5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="235c5-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="235c5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="235c5-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="235c5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
