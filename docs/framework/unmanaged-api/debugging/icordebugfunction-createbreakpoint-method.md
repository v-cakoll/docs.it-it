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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2881b1f420d8e177e093969b2cdd9f2ff36883f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33412519"
---
# <a name="icordebugfunctioncreatebreakpoint-method"></a><span data-ttu-id="329ac-102">Metodo ICorDebugFunction::CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="329ac-102">ICorDebugFunction::CreateBreakpoint Method</span></span>
<span data-ttu-id="329ac-103">Crea un punto di interruzione all'inizio di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="329ac-103">Creates a breakpoint at the beginning of this function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="329ac-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="329ac-104">Syntax</span></span>  
  
```  
HRESULT CreateBreakpoint (  
    [out] ICorDebugFunctionBreakpoint **ppBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="329ac-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="329ac-105">Parameters</span></span>  
 `ppBreakpoint`  
 <span data-ttu-id="329ac-106">[out] Un puntatore all'indirizzo di un oggetto ICorDebugFunctionBreakpoint che rappresenta il nuovo punto di interruzione per la funzione.</span><span class="sxs-lookup"><span data-stu-id="329ac-106">[out] A pointer to the address of an ICorDebugFunctionBreakpoint object that represents the new breakpoint for the function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="329ac-107">Requisiti</span><span class="sxs-lookup"><span data-stu-id="329ac-107">Requirements</span></span>  
 <span data-ttu-id="329ac-108">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="329ac-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="329ac-109">**Intestazione:** Cordebug. idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="329ac-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="329ac-110">**Libreria:** CorGuids. lib</span><span class="sxs-lookup"><span data-stu-id="329ac-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="329ac-111">**Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="329ac-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
