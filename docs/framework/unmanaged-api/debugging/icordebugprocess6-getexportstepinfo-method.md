---
title: Metodo ICorDebugProcess6::GetExportStepInfo
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dbb0e1cf904675005522002596476aec996124b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="6f88c-102">Metodo ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="6f88c-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="6f88c-103">Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="6f88c-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f88c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="6f88c-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6f88c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="6f88c-105">Parameters</span></span>  
 <span data-ttu-id="6f88c-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="6f88c-106">pszExportName</span></span>  
 <span data-ttu-id="6f88c-107">[in] Il nome di una funzione di runtime di esportazione così come è scritta nella tabella di esportazione PE.</span><span class="sxs-lookup"><span data-stu-id="6f88c-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="6f88c-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="6f88c-108">invokeKind</span></span>  
 <span data-ttu-id="6f88c-109">[out] Un puntatore a un membro del [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumerazione che descrive come la funzione esportata richiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6f88c-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="6f88c-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="6f88c-110">invokePurpose</span></span>  
 <span data-ttu-id="6f88c-111">[out] Un puntatore a un membro del [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumerazione che descrive perché la funzione esportata chiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="6f88c-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6f88c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6f88c-112">Return Value</span></span>  
 <span data-ttu-id="6f88c-113">Il metodo può restituire i valori elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="6f88c-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="6f88c-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="6f88c-114">Return value</span></span>|<span data-ttu-id="6f88c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="6f88c-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="6f88c-116">La chiamata al metodo è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="6f88c-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="6f88c-117">`pInvokeKind`o `pInvokePurpose` è **null**.</span><span class="sxs-lookup"><span data-stu-id="6f88c-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="6f88c-118">Altri valori di `HRESULT` con errori.</span><span class="sxs-lookup"><span data-stu-id="6f88c-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="6f88c-119">A seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="6f88c-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f88c-120">Note</span><span class="sxs-lookup"><span data-stu-id="6f88c-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6f88c-121">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="6f88c-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f88c-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="6f88c-122">Requirements</span></span>  
 <span data-ttu-id="6f88c-123">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f88c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f88c-124">**Intestazione:** CorDebug.idl, Cordebug. H</span><span class="sxs-lookup"><span data-stu-id="6f88c-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f88c-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f88c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f88c-126">**Versioni di .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f88c-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f88c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6f88c-127">See Also</span></span>  
 [<span data-ttu-id="6f88c-128">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="6f88c-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)  
 [<span data-ttu-id="6f88c-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="6f88c-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
