---
title: Metodo ICorDebugCode::GetAddress
ms.date: 03/30/2017
api_name:
- ICorDebugCode.GetAddress
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode::GetAddress
helpviewer_keywords:
- GetAddress method, ICorDebugCode interface [.NET Framework debugging]
- ICorDebugCode::GetAddress method [.NET Framework debugging]
ms.assetid: cc507cb0-df2e-49c2-b32e-0c3271a8df9a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7df668487601e4278b56e196a43d1154b643fd29
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700739"
---
# <a name="icordebugcodegetaddress-method"></a><span data-ttu-id="5cd11-102">Metodo ICorDebugCode::GetAddress</span><span class="sxs-lookup"><span data-stu-id="5cd11-102">ICorDebugCode::GetAddress Method</span></span>
<span data-ttu-id="5cd11-103">Ottiene l'indirizzo RVA (relativo Virtual Address) del segmento di codice rappresentato da questa interfaccia "ICorDebugCode".</span><span class="sxs-lookup"><span data-stu-id="5cd11-103">Gets the relative virtual address (RVA) of the code segment that this "ICorDebugCode" interface represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd11-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5cd11-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAddress (  
    [out] CORDB_ADDRESS *pStart  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cd11-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="5cd11-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="5cd11-106">out Puntatore all'RVA del segmento di codice.</span><span class="sxs-lookup"><span data-stu-id="5cd11-106">[out] A pointer to the RVA of the code segment.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cd11-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5cd11-107">Requirements</span></span>  
 <span data-ttu-id="5cd11-108">**Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5cd11-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cd11-109">**Intestazione:** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="5cd11-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5cd11-110">**Libreria** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5cd11-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5cd11-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cd11-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
