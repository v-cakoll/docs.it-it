---
title: Metodo ICorDebugClass::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 205b7670bac55d428d7458b7accaee5e00b00b03
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745577"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="d3a2a-102">Metodo ICorDebugClass::GetModule</span><span class="sxs-lookup"><span data-stu-id="d3a2a-102">ICorDebugClass::GetModule Method</span></span>
<span data-ttu-id="d3a2a-103">Ottiene il modulo che definisce la classe.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-103">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3a2a-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d3a2a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d3a2a-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d3a2a-105">Parameters</span></span>  
 `pModule`  
 <span data-ttu-id="d3a2a-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugModule che rappresenta il modulo in cui questa classe è definita.</span><span class="sxs-lookup"><span data-stu-id="d3a2a-106">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d3a2a-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d3a2a-107">Requirements</span></span>  
 <span data-ttu-id="d3a2a-108">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3a2a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3a2a-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d3a2a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d3a2a-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3a2a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3a2a-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3a2a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
