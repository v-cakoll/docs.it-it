---
title: Metodo ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 6580fdaacaea17fcf886bfd7ac5e236925acf453
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178522"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="38e0c-102">Metodo ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="38e0c-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="38e0c-103">Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="38e0c-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38e0c-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="38e0c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38e0c-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="38e0c-105">Parameters</span></span>  
 <span data-ttu-id="38e0c-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="38e0c-106">pszExportName</span></span>  
 <span data-ttu-id="38e0c-107">[in] Il nome di una funzione di runtime di esportazione così come è scritta nella tabella di esportazione PE.</span><span class="sxs-lookup"><span data-stu-id="38e0c-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="38e0c-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="38e0c-108">invokeKind</span></span>  
 <span data-ttu-id="38e0c-109">[fuori] Puntatore a un membro dell'enumerazione [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) che descrive come la funzione esportata richiamerà il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="38e0c-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="38e0c-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="38e0c-110">invokePurpose</span></span>  
 <span data-ttu-id="38e0c-111">[fuori] Puntatore a un membro dell'enumerazione [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) che descrive il motivo per cui la funzione esportata chiamerà codice gestito.</span><span class="sxs-lookup"><span data-stu-id="38e0c-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="38e0c-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="38e0c-112">Return Value</span></span>  
 <span data-ttu-id="38e0c-113">Il metodo può restituire i valori elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="38e0c-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="38e0c-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="38e0c-114">Return value</span></span>|<span data-ttu-id="38e0c-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="38e0c-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="38e0c-116">La chiamata al metodo è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="38e0c-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="38e0c-117">`pInvokeKind`o `pInvokePurpose` è **null**.</span><span class="sxs-lookup"><span data-stu-id="38e0c-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="38e0c-118">Altri valori di `HRESULT` con errori.</span><span class="sxs-lookup"><span data-stu-id="38e0c-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="38e0c-119">A seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="38e0c-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38e0c-120">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="38e0c-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38e0c-121">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="38e0c-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38e0c-122">Requisiti</span><span class="sxs-lookup"><span data-stu-id="38e0c-122">Requirements</span></span>  
 <span data-ttu-id="38e0c-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38e0c-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38e0c-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38e0c-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38e0c-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38e0c-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38e0c-126">**Versioni di .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38e0c-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38e0c-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="38e0c-127">See also</span></span>

- [<span data-ttu-id="38e0c-128">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="38e0c-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="38e0c-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="38e0c-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
