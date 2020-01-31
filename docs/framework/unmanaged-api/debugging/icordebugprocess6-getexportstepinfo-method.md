---
title: Metodo ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 118f52db63464b4c9355ba9ee7f330b996c5bf71
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792239"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a><span data-ttu-id="10acf-102">Metodo ICorDebugProcess6::GetExportStepInfo</span><span class="sxs-lookup"><span data-stu-id="10acf-102">ICorDebugProcess6::GetExportStepInfo Method</span></span>
<span data-ttu-id="10acf-103">Fornisce informazioni sulle funzioni di runtime esportate per consentire l'esecuzione di codice gestito seguendo un'istruzione alla volta.</span><span class="sxs-lookup"><span data-stu-id="10acf-103">Provides information on runtime exported functions to help step through managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="10acf-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="10acf-104">Syntax</span></span>  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,   
    [out] CorDebugCodeInvokeKind* pInvokeKind,   
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a><span data-ttu-id="10acf-105">Parametri</span><span class="sxs-lookup"><span data-stu-id="10acf-105">Parameters</span></span>  
 <span data-ttu-id="10acf-106">pszExportName</span><span class="sxs-lookup"><span data-stu-id="10acf-106">pszExportName</span></span>  
 <span data-ttu-id="10acf-107">[in] Il nome di una funzione di runtime di esportazione così come è scritta nella tabella di esportazione PE.</span><span class="sxs-lookup"><span data-stu-id="10acf-107">[in] The name of a runtime export function as written in the PE export table.</span></span>  
  
 <span data-ttu-id="10acf-108">invokeKind</span><span class="sxs-lookup"><span data-stu-id="10acf-108">invokeKind</span></span>  
 <span data-ttu-id="10acf-109">out Puntatore a un membro dell'enumerazione [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) che descrive il modo in cui la funzione esportata richiama il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="10acf-109">[out] A pointer to a member of the [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeration that describes how the exported function will invoke managed code.</span></span>  
  
 <span data-ttu-id="10acf-110">invokePurpose</span><span class="sxs-lookup"><span data-stu-id="10acf-110">invokePurpose</span></span>  
 <span data-ttu-id="10acf-111">out Puntatore a un membro dell'enumerazione [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) che descrive il motivo per cui la funzione esportata chiamerà il codice gestito.</span><span class="sxs-lookup"><span data-stu-id="10acf-111">[out] A pointer to a member of the [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeration that describes why the exported function will call managed code.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="10acf-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="10acf-112">Return Value</span></span>  
 <span data-ttu-id="10acf-113">Il metodo può restituire i valori elencati nella seguente tabella.</span><span class="sxs-lookup"><span data-stu-id="10acf-113">The method can return the values listed in the following table.</span></span>  
  
|<span data-ttu-id="10acf-114">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="10acf-114">Return value</span></span>|<span data-ttu-id="10acf-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="10acf-115">Description</span></span>|  
|------------------|-----------------|  
|`S_OK`|<span data-ttu-id="10acf-116">La chiamata al metodo è stata completata correttamente.</span><span class="sxs-lookup"><span data-stu-id="10acf-116">The method call was successful.</span></span>|  
|`E_POINTER`|<span data-ttu-id="10acf-117">`pInvokeKind` o `pInvokePurpose` è **null**.</span><span class="sxs-lookup"><span data-stu-id="10acf-117">`pInvokeKind` or `pInvokePurpose` is **null**.</span></span>|  
|<span data-ttu-id="10acf-118">Altri valori di `HRESULT` con errori.</span><span class="sxs-lookup"><span data-stu-id="10acf-118">Other failing `HRESULT` values.</span></span>|<span data-ttu-id="10acf-119">A seconda dei casi.</span><span class="sxs-lookup"><span data-stu-id="10acf-119">As appropriate.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="10acf-120">Note</span><span class="sxs-lookup"><span data-stu-id="10acf-120">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="10acf-121">Questo metodo è disponibile solo con .NET Native.</span><span class="sxs-lookup"><span data-stu-id="10acf-121">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="10acf-122">Requisiti di</span><span class="sxs-lookup"><span data-stu-id="10acf-122">Requirements</span></span>  
 <span data-ttu-id="10acf-123">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="10acf-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="10acf-124">**Intestazione:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="10acf-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="10acf-125">**Libreria:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="10acf-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="10acf-126">**Versioni .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="10acf-126">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10acf-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="10acf-127">See also</span></span>

- [<span data-ttu-id="10acf-128">Interfaccia ICorDebugProcess6</span><span class="sxs-lookup"><span data-stu-id="10acf-128">ICorDebugProcess6 Interface</span></span>](icordebugprocess6-interface.md)
- [<span data-ttu-id="10acf-129">Interfacce di debug</span><span class="sxs-lookup"><span data-stu-id="10acf-129">Debugging Interfaces</span></span>](debugging-interfaces.md)
