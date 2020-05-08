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
ms.openlocfilehash: e6e8eb91bbc41faf0dcea010da9aa54995058653
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894982"
---
# <a name="icordebugarrayvaluehasbaseindicies-method"></a><span data-ttu-id="f58d5-102">Metodo ICorDebugArrayValue::HasBaseIndicies</span><span class="sxs-lookup"><span data-stu-id="f58d5-102">ICorDebugArrayValue::HasBaseIndicies Method</span></span>
<span data-ttu-id="f58d5-103">Ottiene un valore che indica se le dimensioni di questa matrice hanno un indice di base di diverso da zero.</span><span class="sxs-lookup"><span data-stu-id="f58d5-103">Gets a value that indicates whether any dimensions of this array have a base index of non-zero.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f58d5-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="f58d5-104">Syntax</span></span>  
  
```cpp  
HRESULT HasBaseIndicies (  
    [out] BOOL    *pbHasBaseIndicies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f58d5-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="f58d5-105">Parameters</span></span>  
 `pbHasBaseIndicies`  
 <span data-ttu-id="f58d5-106">out Puntatore a un valore booleano che è `true` se una o più dimensioni di questo `ICorDebugArrayValue` oggetto hanno un indice di base di diverso da zero; in caso contrario, il valore `false`booleano è.</span><span class="sxs-lookup"><span data-stu-id="f58d5-106">[out] A pointer to a Boolean value that is `true` if one or more dimensions of this `ICorDebugArrayValue` object have a base index of non-zero; otherwise, the Boolean value is `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f58d5-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f58d5-107">Requirements</span></span>  
 <span data-ttu-id="f58d5-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f58d5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f58d5-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f58d5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f58d5-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f58d5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f58d5-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f58d5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>
