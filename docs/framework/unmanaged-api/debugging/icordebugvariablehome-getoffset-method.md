---
title: 'Metodo ICorDebugVariableHome:: GetOffset'
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetOffset
helpviewer_keywords:
- ICorDebugVariableHome::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: f025c2e5-3f6c-4be8-9ffe-c8b214617dfe
topic_type:
- apiref
ms.openlocfilehash: 3af8c925b80b9fd4ed0a46d2bd50fe37a6f3154a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125101"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="8ba46-102">Metodo ICorDebugVariableHome:: GetOffset</span><span class="sxs-lookup"><span data-stu-id="8ba46-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="8ba46-103">Ottiene l'offset dal registro di base per una variabile.</span><span class="sxs-lookup"><span data-stu-id="8ba46-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ba46-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8ba46-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8ba46-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="8ba46-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="8ba46-106">out Offset dal registro di base.</span><span class="sxs-lookup"><span data-stu-id="8ba46-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8ba46-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8ba46-107">Return Value</span></span>  
 <span data-ttu-id="8ba46-108">Il metodo restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="8ba46-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="8ba46-109">Value</span><span class="sxs-lookup"><span data-stu-id="8ba46-109">Value</span></span>|<span data-ttu-id="8ba46-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8ba46-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="8ba46-111">La variabile si trova in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="8ba46-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="8ba46-112">La variabile non si trova in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="8ba46-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8ba46-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8ba46-113">Requirements</span></span>  
 <span data-ttu-id="8ba46-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8ba46-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ba46-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8ba46-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8ba46-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8ba46-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8ba46-117">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ba46-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ba46-118">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8ba46-118">See also</span></span>

- [<span data-ttu-id="8ba46-119">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="8ba46-119">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
