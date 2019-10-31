---
title: Metodo ICorDebugFunction::CreateBreakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.CreateBreakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::CreateBreakpoint
helpviewer_keywords:
- ICorDebugFunction::CreateBreakpoint method [.NET Framework debugging]
- CreateBreakpoint method, ICorDebugFunction interface [.NET Framework debugging]
ms.assetid: ffd0f708-0d21-4fae-a395-63b6c45828fa
topic_type:
- apiref
ms.openlocfilehash: 64304b671532325bdc2f8841a2702d537d143330
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124043"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="b5600-102">Metodo ICorDebugFunction::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="b5600-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="b5600-103">Crea un punto di interruzione all'inizio di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="b5600-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b5600-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="b5600-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b5600-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="b5600-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="b5600-106">out Puntatore all'indirizzo di un oggetto ICorDebugFunctionBreakpoint che rappresenta il nuovo punto di interruzione per la funzione.</span><span class="sxs-lookup"><span data-stu-id="b5600-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b5600-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="b5600-107">Requirements</span></span>  
 <span data-ttu-id="b5600-108">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b5600-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b5600-109">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b5600-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b5600-110">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b5600-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b5600-111">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b5600-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
