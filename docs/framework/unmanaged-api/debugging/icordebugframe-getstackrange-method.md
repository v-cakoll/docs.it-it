---
title: Metodo ICorDebugFrame::GetStackRange
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetStackRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetStackRange
helpviewer_keywords:
- GetStackRange method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetStackRange method [.NET Framework debugging]
ms.assetid: fab037cb-fda6-40fb-9367-921e435dd5a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c9f58e66286f5e3e169507efd2f87ce10e9d323b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67754861"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="d4da6-102">Metodo ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="d4da6-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="d4da6-103">Ottiene l'intervallo di indirizzi assoluti dello stack frame corrente.</span><span class="sxs-lookup"><span data-stu-id="d4da6-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4da6-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d4da6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,   
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d4da6-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="d4da6-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="d4da6-106">[out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo iniziale del frame dello stack rappresentato da questo `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="d4da6-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="d4da6-107">[out] Un puntatore a un `CORDB_ADDRESS` che specifica l'indirizzo finale del frame dello stack rappresentato da questo `ICorDebugFrame` oggetto.</span><span class="sxs-lookup"><span data-stu-id="d4da6-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4da6-108">Note</span><span class="sxs-lookup"><span data-stu-id="d4da6-108">Remarks</span></span>  
 <span data-ttu-id="d4da6-109">L'intervallo di indirizzi dello stack è utile per riunire tracce dello stack con interfoliazione raccolte da più motori di debug.</span><span class="sxs-lookup"><span data-stu-id="d4da6-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="d4da6-110">L'intervallo numerico non fornisce informazioni sul contenuto del frame dello stack.</span><span class="sxs-lookup"><span data-stu-id="d4da6-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="d4da6-111">È significativo solo per il confronto dei percorsi dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="d4da6-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4da6-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="d4da6-112">Requirements</span></span>  
 <span data-ttu-id="d4da6-113">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4da6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4da6-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d4da6-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d4da6-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4da6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4da6-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4da6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
