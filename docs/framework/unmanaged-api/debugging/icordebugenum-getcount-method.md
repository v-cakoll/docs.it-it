---
title: Metodo ICorDebugEnum::GetCount
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.GetCount
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type:
- apiref
ms.openlocfilehash: 90ba690897abced2d4f6282eedef91712d8ceeca
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976343"
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="00c9b-102">Metodo ICorDebugEnum::GetCount</span><span class="sxs-lookup"><span data-stu-id="00c9b-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="00c9b-103">Ottiene il numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="00c9b-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00c9b-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="00c9b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00c9b-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="00c9b-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="00c9b-106">out Puntatore al numero di elementi nell'enumerazione.</span><span class="sxs-lookup"><span data-stu-id="00c9b-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00c9b-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="00c9b-107">Requirements</span></span>  
 <span data-ttu-id="00c9b-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00c9b-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00c9b-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00c9b-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00c9b-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00c9b-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00c9b-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00c9b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
