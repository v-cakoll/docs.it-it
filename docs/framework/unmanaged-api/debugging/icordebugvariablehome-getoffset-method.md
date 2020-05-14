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
ms.openlocfilehash: 75a165e2fd517f36d779a934a5bdd9c41956411a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396757"
---
# <a name="icordebugvariablehomegetoffset-method"></a><span data-ttu-id="2c4c4-102">Metodo ICorDebugVariableHome:: GetOffset</span><span class="sxs-lookup"><span data-stu-id="2c4c4-102">ICorDebugVariableHome::GetOffset Method</span></span>
<span data-ttu-id="2c4c4-103">Ottiene l'offset dal registro di base per una variabile.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-103">Gets the offset from the base register for a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c4c4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="2c4c4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset(  
    [out] LONG *pOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c4c4-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="2c4c4-105">Parameters</span></span>  
 `pOffset`  
 <span data-ttu-id="2c4c4-106">out Offset dal registro di base.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-106">[out] The offset from the base register.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c4c4-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="2c4c4-107">Return Value</span></span>  
 <span data-ttu-id="2c4c4-108">Il metodo restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2c4c4-108">The method returns the following values:</span></span>  
  
|<span data-ttu-id="2c4c4-109">Valore</span><span class="sxs-lookup"><span data-stu-id="2c4c4-109">Value</span></span>|<span data-ttu-id="2c4c4-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2c4c4-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="2c4c4-111">La variabile si trova in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-111">The variable is in a register-relative memory location.</span></span>|  
|`E_FAIL`|<span data-ttu-id="2c4c4-112">La variabile non si trova in una posizione di memoria relativa al registro.</span><span class="sxs-lookup"><span data-stu-id="2c4c4-112">The variable is not in a register-relative memory location.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2c4c4-113">Requisiti</span><span class="sxs-lookup"><span data-stu-id="2c4c4-113">Requirements</span></span>  
 <span data-ttu-id="2c4c4-114">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2c4c4-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2c4c4-115">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2c4c4-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2c4c4-116">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2c4c4-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2c4c4-117">**Versioni .NET Framework:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2c4c4-117">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c4c4-118">Vedi anche</span><span class="sxs-lookup"><span data-stu-id="2c4c4-118">See also</span></span>

- [<span data-ttu-id="2c4c4-119">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="2c4c4-119">ICorDebugVariableHome Interface</span></span>](icordebugvariablehome-interface.md)
