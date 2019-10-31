---
title: Metodo ICorDebugType::GetRank
ms.date: 03/30/2017
api_name:
- ICorDebugType.GetRank
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetRank
helpviewer_keywords:
- GetRank method, ICorDebugType interface [.NET Framework debugging]
- ICorDebugType::GetRank method [.NET Framework debugging]
ms.assetid: 72d3d927-f590-4f2d-8f60-448f3dfb96af
topic_type:
- apiref
ms.openlocfilehash: 9a00177faabfcad56d70ec5c64328c90675c1532
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138766"
---
# <a name="icordebugtypegetrank-method"></a><span data-ttu-id="b9e89-102">Metodo ICorDebugType::GetRank</span><span class="sxs-lookup"><span data-stu-id="b9e89-102">ICorDebugType::GetRank Method</span></span>
<span data-ttu-id="b9e89-103">Ottiene il numero di dimensioni in un tipo di matrice.</span><span class="sxs-lookup"><span data-stu-id="b9e89-103">Gets the number of dimensions in an array type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9e89-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b9e89-104">Syntax</span></span>  
  
```cpp  
HRESULT GetRank (  
    [out] ULONG32   *pnRank  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9e89-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b9e89-105">Parameters</span></span>  
 `pnRank`  
 <span data-ttu-id="b9e89-106">out Puntatore al numero di dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b9e89-106">[out] A pointer to the number of dimensions.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9e89-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b9e89-107">Requirements</span></span>  
 <span data-ttu-id="b9e89-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9e89-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9e89-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9e89-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9e89-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9e89-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9e89-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9e89-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
