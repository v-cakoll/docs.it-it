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
ms.openlocfilehash: 7a35ce025360e0ec8b7085d68e54548026b7c7fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178904"
---
# <a name="icordebugframegetstackrange-method"></a><span data-ttu-id="4d48d-102">Metodo ICorDebugFrame::GetStackRange</span><span class="sxs-lookup"><span data-stu-id="4d48d-102">ICorDebugFrame::GetStackRange Method</span></span>
<span data-ttu-id="4d48d-103">Ottiene l'intervallo di indirizzi assoluto di questo stack frame.</span><span class="sxs-lookup"><span data-stu-id="4d48d-103">Gets the absolute address range of this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d48d-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="4d48d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStackRange (  
    [out] CORDB_ADDRESS      *pStart,
    [out] CORDB_ADDRESS      *pEnd  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d48d-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="4d48d-105">Parameters</span></span>  
 `pStart`  
 <span data-ttu-id="4d48d-106">[fuori] Puntatore a `CORDB_ADDRESS` un oggetto che specifica l'indirizzo `ICorDebugFrame` iniziale dello stack frame rappresentato da questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="4d48d-106">[out] A pointer to a `CORDB_ADDRESS` that specifies the starting address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
 `pEnd`  
 <span data-ttu-id="4d48d-107">[fuori] Puntatore a `CORDB_ADDRESS` un oggetto che specifica l'indirizzo `ICorDebugFrame` finale dello stack frame rappresentato da questo oggetto.</span><span class="sxs-lookup"><span data-stu-id="4d48d-107">[out] A pointer to a `CORDB_ADDRESS` that specifies the ending address of the stack frame represented by this `ICorDebugFrame` object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4d48d-108">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="4d48d-108">Remarks</span></span>  
 <span data-ttu-id="4d48d-109">L'intervallo di indirizzi dello stack è utile per unire le tracce dello stack interfogliate raccolte da più motori di debug.</span><span class="sxs-lookup"><span data-stu-id="4d48d-109">The address range of the stack is useful for piecing together interleaved stack traces gathered from multiple debugging engines.</span></span> <span data-ttu-id="4d48d-110">L'intervallo numerico non fornisce informazioni sul contenuto dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="4d48d-110">The numeric range provides no information about the contents of the stack frame.</span></span> <span data-ttu-id="4d48d-111">È significativo solo per il confronto delle posizioni dello stack frame.</span><span class="sxs-lookup"><span data-stu-id="4d48d-111">It is meaningful only for comparison of stack frame locations.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d48d-112">Requisiti</span><span class="sxs-lookup"><span data-stu-id="4d48d-112">Requirements</span></span>  
 <span data-ttu-id="4d48d-113">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d48d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d48d-114">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d48d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d48d-115">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d48d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d48d-116">**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d48d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
