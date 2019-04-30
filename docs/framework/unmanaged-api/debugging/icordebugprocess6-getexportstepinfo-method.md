---
title: Metodo ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 44a891e6d65d159875f5607ac33b0668414cb380
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61948624"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="3f884-102">Metodo ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="3f884-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="3f884-103">Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="3f884-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3f884-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="3f884-104">Syntax</span></span>  
  
```  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3f884-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="3f884-105">Parameters</span></span>  
 <span data-ttu-id="3f884-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="3f884-106">pszExportName</span></span>  
 <span data-ttu-id="3f884-107">[in] Il nome di una funzione di runtime di esportazione così come è scritta nella tabella di esportazione PE.</span><span class="sxs-lookup"><span data-stu-id="3f884-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="3f884-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="3f884-108">invokeKind</span></span>  
 <span data-ttu-id="3f884-109">[out] Un puntatore a un membro del [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumerazione che descrive il modo in cui la funzione esportata richiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3f884-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="3f884-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="3f884-110">invokePurpose</span></span>  
 <span data-ttu-id="3f884-111">[out] Un puntatore a un membro del [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumerazione che descrive il motivo per cui la funzione esportata chiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="3f884-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](../../../../docs/framework/unmanaged-api/debugging/cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3f884-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f884-112">Return Value</span></span>  
 <span data-ttu-id="3f884-113">Il metodo può restituire i valori elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="3f884-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="3f884-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="3f884-114">Return value</span></span>|<span data-ttu-id="3f884-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3f884-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="3f884-116">La chiamata al metodo è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="3f884-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="3f884-117">`pInvokeKind` oppure `pInvokePurpose` viene **null**.</span><span class="sxs-lookup"><span data-stu-id="3f884-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="3f884-118">Altri valori di `HRESULT` con errori.</span><span class="sxs-lookup"><span data-stu-id="3f884-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="3f884-119">A seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="3f884-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3f884-120">Note</span><span class="sxs-lookup"><span data-stu-id="3f884-120">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3f884-121">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="3f884-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3f884-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="3f884-122">Requirements</span></span>  
 <span data-ttu-id="3f884-123">**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3f884-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3f884-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3f884-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3f884-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3f884-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3f884-126">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3f884-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3f884-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3f884-127">See also</span></span>

- [<span data-ttu-id="3f884-128">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="3f884-128">ICorDebugProcess6 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-interface.md)
- [<span data-ttu-id="3f884-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="3f884-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
