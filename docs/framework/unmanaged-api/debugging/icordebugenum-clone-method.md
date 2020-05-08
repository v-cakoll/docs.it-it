---
title: Metodo ICorDebugEnum::Clone
ms.date: 03/30/2017
api_name:
- ICorDebugEnum.Clone
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum::Clone
helpviewer_keywords:
- Clone method, ICorDebugEnum interface [.NET Framework debugging]
- ICorDebugEnum::Clone method [.NET Framework debugging]
ms.assetid: 57eefaf3-75cf-4496-bc94-88c0706861b7
topic_type:
- apiref
ms.openlocfilehash: 9f0fda803ba3a1ce35017d85e84b3bf6f567eda0
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "82976369"
---
# <a name="icordebugenumclone-method"></a><span data-ttu-id="dcbe4-102">Metodo ICorDebugEnum::Clone</span><span class="sxs-lookup"><span data-stu-id="dcbe4-102">ICorDebugEnum::Clone Method</span></span>
<span data-ttu-id="dcbe4-103">Crea una copia di questo oggetto ICorDebugEnum.</span><span class="sxs-lookup"><span data-stu-id="dcbe4-103">Creates a copy of this ICorDebugEnum object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dcbe4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="dcbe4-104">Syntax</span></span>  
  
```cpp  
HRESULT Clone (  
    [out] ICorDebugEnum **ppEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dcbe4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="dcbe4-105">Parameters</span></span>  
 `ppEnum`  
 <span data-ttu-id="dcbe4-106">out Puntatore all'indirizzo di un `ICorDebugEnum` oggetto che è una copia di questo `ICorDebugEnum` oggetto.</span><span class="sxs-lookup"><span data-stu-id="dcbe4-106">[out] A pointer to the address of an `ICorDebugEnum` object that is a copy of this `ICorDebugEnum` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dcbe4-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="dcbe4-107">Requirements</span></span>  
 <span data-ttu-id="dcbe4-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dcbe4-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dcbe4-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dcbe4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dcbe4-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dcbe4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dcbe4-111">**Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dcbe4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
