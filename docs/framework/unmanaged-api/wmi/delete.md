---
title: Eliminare la funzione (riferimenti alle API non gestite)
description: "La funzione Delete Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: Delete
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: Delete
helpviewer_keywords: Delete function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f32487d2bd59bd76acdc32218c6bb0842de20e87
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="delete-function"></a><span data-ttu-id="438ee-103">Eliminare la funzione</span><span class="sxs-lookup"><span data-stu-id="438ee-103">Delete function</span></span>
<span data-ttu-id="438ee-104">Elimina la proprietà specificata e tutti i relativi qualificatori da una definizione di classe CIM.</span><span class="sxs-lookup"><span data-stu-id="438ee-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="438ee-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="438ee-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="438ee-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="438ee-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="438ee-107">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="438ee-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="438ee-108">[in] Un puntatore a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="438ee-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="438ee-109">[in] Il nome della proprietà da eliminare.</span><span class="sxs-lookup"><span data-stu-id="438ee-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="438ee-110">`wszName`deve essere un puntatore a un oggetto valido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="438ee-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="438ee-111">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="438ee-111">Return value</span></span>

<span data-ttu-id="438ee-112">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="438ee-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="438ee-113">Costante</span><span class="sxs-lookup"><span data-stu-id="438ee-113">Constant</span></span>  |<span data-ttu-id="438ee-114">Valore</span><span class="sxs-lookup"><span data-stu-id="438ee-114">Value</span></span>  |<span data-ttu-id="438ee-115">Descrizione</span><span class="sxs-lookup"><span data-stu-id="438ee-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="438ee-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="438ee-116">0x80041001</span></span> | <span data-ttu-id="438ee-117">Si è verificato un errore non specificato.</span><span class="sxs-lookup"><span data-stu-id="438ee-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="438ee-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="438ee-118">0x80041016</span></span> | <span data-ttu-id="438ee-119">La proprietà non può essere eliminata.</span><span class="sxs-lookup"><span data-stu-id="438ee-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="438ee-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="438ee-120">0x80041008</span></span> | <span data-ttu-id="438ee-121">`wszzName` non è valido.</span><span class="sxs-lookup"><span data-stu-id="438ee-121">`wszzName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="438ee-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="438ee-122">0x80041002</span></span> | <span data-ttu-id="438ee-123">La proprietà specificata non esiste.</span><span class="sxs-lookup"><span data-stu-id="438ee-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="438ee-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="438ee-124">0x80041006</span></span> | <span data-ttu-id="438ee-125">Non è disponibile memoria sufficiente per completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="438ee-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="438ee-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="438ee-126">0x8004101c</span></span> | <span data-ttu-id="438ee-127">La proprietà viene ereditata da una classe base.</span><span class="sxs-lookup"><span data-stu-id="438ee-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="438ee-128">La proprietà è una proprietà di sistema.</span><span class="sxs-lookup"><span data-stu-id="438ee-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="438ee-129">0</span><span class="sxs-lookup"><span data-stu-id="438ee-129">0</span></span> | <span data-ttu-id="438ee-130">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="438ee-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="438ee-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="438ee-131">0x80041030</span></span> | <span data-ttu-id="438ee-132">La funzione eliminata di un valore predefinito di sostituzione per la classe corrente.</span><span class="sxs-lookup"><span data-stu-id="438ee-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="438ee-133">Il valore predefinito per questa proprietà nella classe padre è stata reactiviated.</span><span class="sxs-lookup"><span data-stu-id="438ee-133">The default value for this property in the parent class has been reactiviated.</span></span> | 

## <a name="remarks"></a><span data-ttu-id="438ee-134">Note</span><span class="sxs-lookup"><span data-stu-id="438ee-134">Remarks</span></span>

<span data-ttu-id="438ee-135">Questa funzione esegue il wrapping di una chiamata al [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="438ee-135">This function wraps a call to the [IWbemClassObject::Delete](https://msdn.microsoft.com/library/aa391438(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="438ee-136">Requisiti</span><span class="sxs-lookup"><span data-stu-id="438ee-136">Requirements</span></span>  
 <span data-ttu-id="438ee-137">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="438ee-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="438ee-138">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="438ee-138">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="438ee-139">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="438ee-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="438ee-140">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="438ee-140">See also</span></span>  
[<span data-ttu-id="438ee-141">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="438ee-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
