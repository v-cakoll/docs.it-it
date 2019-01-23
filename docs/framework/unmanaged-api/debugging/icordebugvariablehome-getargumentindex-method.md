---
title: Metodo ICorDebugVariableHome::GetArgumentIndex
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHome.GetArgumentIndex
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 163704bf9a71ceda04bdfd73f9ca676c19d8a62c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526640"
---
# <a name="icordebugvariablehomegetargumentindex-method"></a><span data-ttu-id="ca982-102">Metodo ICorDebugVariableHome::GetArgumentIndex</span><span class="sxs-lookup"><span data-stu-id="ca982-102">ICorDebugVariableHome::GetArgumentIndex Method</span></span>
<span data-ttu-id="ca982-103">Ottiene l'indice di un argomento di funzione.</span><span class="sxs-lookup"><span data-stu-id="ca982-103">Gets the index of a function argument.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca982-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ca982-104">Syntax</span></span>  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ca982-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="ca982-105">Parameters</span></span>  
 `pArgumentIndex`  
 <span data-ttu-id="ca982-106">[out] Un puntatore all'indice di argomento.</span><span class="sxs-lookup"><span data-stu-id="ca982-106">[out] A pointer to the argument index.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ca982-107">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ca982-107">Return Value</span></span>  
 <span data-ttu-id="ca982-108">Il metodo restituisce i valori seguenti.</span><span class="sxs-lookup"><span data-stu-id="ca982-108">The method returns the following values.</span></span>  
  
|<span data-ttu-id="ca982-109">Value</span><span class="sxs-lookup"><span data-stu-id="ca982-109">Value</span></span>|<span data-ttu-id="ca982-110">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ca982-110">Description</span></span>|  
|-----------|-----------------|  
|`S_OK`|<span data-ttu-id="ca982-111">La chiamata al metodo ha restituito un indice di argomento valido.</span><span class="sxs-lookup"><span data-stu-id="ca982-111">The method call returned a valid argument index.</span></span>|  
|`E_FAIL`|<span data-ttu-id="ca982-112">L'oggetto corrente [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) istanza rappresenta una variabile locale.</span><span class="sxs-lookup"><span data-stu-id="ca982-112">The current [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) instance represents a local variable.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ca982-113">Note</span><span class="sxs-lookup"><span data-stu-id="ca982-113">Remarks</span></span>  
 <span data-ttu-id="ca982-114">L'indice dell'argomento è utilizzabile per recuperare i metadati per questo argomento.</span><span class="sxs-lookup"><span data-stu-id="ca982-114">The argument index can be used to retrieve metadata for this argument.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca982-115">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ca982-115">Requirements</span></span>  
 <span data-ttu-id="ca982-116">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ca982-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca982-117">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ca982-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ca982-118">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ca982-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ca982-119">**Versioni di .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca982-119">**.NET Framework Versions:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca982-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ca982-120">See also</span></span>
- [<span data-ttu-id="ca982-121">Interfaccia ICorDebugVariableHome</span><span class="sxs-lookup"><span data-stu-id="ca982-121">ICorDebugVariableHome Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
