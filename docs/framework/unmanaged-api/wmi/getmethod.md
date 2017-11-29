---
title: Funzione GetMethod (riferimenti alle API non gestite)
description: La funzione GetMethod recupera informazioni su un metodo.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetMethod
helpviewer_keywords: GetMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b4e89dabb7f4542a63260445ff2d70edcafc1784
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getmethod-function"></a><span data-ttu-id="0cff4-103">GetMethod (funzione)</span><span class="sxs-lookup"><span data-stu-id="0cff4-103">GetMethod function</span></span>
<span data-ttu-id="0cff4-104">Recupera le informazioni relative al metodo specificato.</span><span class="sxs-lookup"><span data-stu-id="0cff4-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="0cff4-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="0cff4-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="0cff4-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="0cff4-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="0cff4-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="0cff4-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="0cff4-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="0cff4-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="0cff4-109">[in] Il nome del metodo.</span><span class="sxs-lookup"><span data-stu-id="0cff4-109">[in] The method name.</span></span> <span data-ttu-id="0cff4-110">Questo parametro non può essere `null` e deve puntare a un oggetto valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="0cff4-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="0cff4-111">[in] Riservato.</span><span class="sxs-lookup"><span data-stu-id="0cff4-111">[in] Reserved.</span></span> <span data-ttu-id="0cff4-112">Questo parametro deve essere 0.</span><span class="sxs-lookup"><span data-stu-id="0cff4-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="0cff4-113">[out] Un puntatore all'indirizzo di un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza che descrive il paramteers al metodo.</span><span class="sxs-lookup"><span data-stu-id="0cff4-113">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="0cff4-114">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="0cff4-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="0cff4-115">[out] Un puntatore all'indirizzo di un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza che descrive i parametri out al metodo.</span><span class="sxs-lookup"><span data-stu-id="0cff4-115">[out] A pointer to the address of an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="0cff4-116">Questo parametro viene ignorato se è impostato su `null`.</span><span class="sxs-lookup"><span data-stu-id="0cff4-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="0cff4-117">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="0cff4-117">Return value</span></span>

<span data-ttu-id="0cff4-118">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="0cff4-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="0cff4-119">Costante</span><span class="sxs-lookup"><span data-stu-id="0cff4-119">Constant</span></span>  |<span data-ttu-id="0cff4-120">Valore</span><span class="sxs-lookup"><span data-stu-id="0cff4-120">Value</span></span>  |<span data-ttu-id="0cff4-121">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0cff4-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="0cff4-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="0cff4-122">0x80041002</span></span> | <span data-ttu-id="0cff4-123">La proprietà specificata non è stata trovata.</span><span class="sxs-lookup"><span data-stu-id="0cff4-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="0cff4-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="0cff4-124">0x80041006</span></span> | <span data-ttu-id="0cff4-125">Memoria insufficiente è disponibile per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="0cff4-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="0cff4-126">0</span><span class="sxs-lookup"><span data-stu-id="0cff4-126">0</span></span> | <span data-ttu-id="0cff4-127">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="0cff4-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="0cff4-128">Note</span><span class="sxs-lookup"><span data-stu-id="0cff4-128">Remarks</span></span>

<span data-ttu-id="0cff4-129">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="0cff4-129">This function wraps a call to the [IWbemClassObject::GetMethod](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="0cff4-130">Gestione di Windows è possibile impostare il [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) puntatore a `null` se il metodo ha alcun parametro in.</span><span class="sxs-lookup"><span data-stu-id="0cff4-130">Windows Management can set the [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="0cff4-131">In `ppInSignature` e `ppOutSignature` descrivono i parametri, in e out rispettivamente come proprietà in un `IWbemClassObject` istanza della classe di sistema [Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="0cff4-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](https://msdn.microsoft.com/library/aa394667(v=vs.85).aspx).</span></span> <span data-ttu-id="0cff4-132">Le proprietà in `ppInsignature` sono denominati **Param***n*, dove  *n*  è la posizione del parametro nella firma del metodo (ad esempio come `Param1`, `Param2`, ecc.).</span><span class="sxs-lookup"><span data-stu-id="0cff4-132">The properties in `ppInsignature` are named **Param***n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="0cff4-133">Le proprietà in `ppOutSignature` sono denominate anche **Param***n*, e il valore restituito viene denominato **ReturnValue**.</span><span class="sxs-lookup"><span data-stu-id="0cff4-133">The properties in `ppOutSignature` are also named **Param***n*, and the return value is named **ReturnValue**.</span></span> <span data-ttu-id="0cff4-134">Per ulteriori informazioni e un esempio, vedere [IWbemClassObject::GetMethod metodo](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="0cff4-134">For more information and an example, see [IWbemClassObject::GetMethod method](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="0cff4-135">Requisiti</span><span class="sxs-lookup"><span data-stu-id="0cff4-135">Requirements</span></span>  
<span data-ttu-id="0cff4-136">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cff4-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cff4-137">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="0cff4-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="0cff4-138">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0cff4-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cff4-139">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0cff4-139">See also</span></span>  
[<span data-ttu-id="0cff4-140">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="0cff4-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
