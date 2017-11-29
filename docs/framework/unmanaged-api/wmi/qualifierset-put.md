---
title: Funzione QualifierSet_Put (riferimenti alle API non gestite)
description: La funzione QualifierSet_Put scrive qualificatore denominato e il relativo valore.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Put
helpviewer_keywords: QualifierSet_Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7fdb6759d4e39ad9ab6bd6da2c2a0e2abfbe5d56
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="ae820-103">QualifierSet_Put (funzione)</span><span class="sxs-lookup"><span data-stu-id="ae820-103">QualifierSet_Put function</span></span>
<span data-ttu-id="ae820-104">Scrive il qualificatore denominato e il valore.</span><span class="sxs-lookup"><span data-stu-id="ae820-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="ae820-105">Nuovo qualificatore sovrascrive il valore precedente con lo stesso nome.</span><span class="sxs-lookup"><span data-stu-id="ae820-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="ae820-106">Se il qualificatore non esiste, viene creato.</span><span class="sxs-lookup"><span data-stu-id="ae820-106">If the qualifier does not exist, it is created.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ae820-107">Sintassi</span><span class="sxs-lookup"><span data-stu-id="ae820-107">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="ae820-108">Parametri</span><span class="sxs-lookup"><span data-stu-id="ae820-108">Parameters</span></span>

`vFunc`   
<span data-ttu-id="ae820-109">[in] Questo parametro è inutilizzato.</span><span class="sxs-lookup"><span data-stu-id="ae820-109">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="ae820-110">[in] Un puntatore a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) istanza.</span><span class="sxs-lookup"><span data-stu-id="ae820-110">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="ae820-111">[in] Il nome del qualificatore da scrivere.</span><span class="sxs-lookup"><span data-stu-id="ae820-111">[in] The name of the qualifier to write.</span></span>

<span data-ttu-id="ae820-112">`pVal`[in] Un puntatore a un oggetto valido `VARIANT` che contiene il qualificatore da scrivere.</span><span class="sxs-lookup"><span data-stu-id="ae820-112">`pVal` [in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="ae820-113">Questo parametro non può essere `null`.</span><span class="sxs-lookup"><span data-stu-id="ae820-113">This parameter cannot be `null`.</span></span>

<span data-ttu-id="ae820-114">`lFlavor`[in] Una delle costanti seguenti che definisce i tipi di qualificatore desiderato per il qualificatore.</span><span class="sxs-lookup"><span data-stu-id="ae820-114">`lFlavor` [in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="ae820-115">Il valore predefinito è `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="ae820-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="ae820-116">Costante</span><span class="sxs-lookup"><span data-stu-id="ae820-116">Constant</span></span>  |<span data-ttu-id="ae820-117">Valore</span><span class="sxs-lookup"><span data-stu-id="ae820-117">Value</span></span>  |<span data-ttu-id="ae820-118">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae820-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="ae820-119">0</span><span class="sxs-lookup"><span data-stu-id="ae820-119">0</span></span> | <span data-ttu-id="ae820-120">Il qualificatore può essere sottoposto a override in una classe derivata o istanza.</span><span class="sxs-lookup"><span data-stu-id="ae820-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="ae820-121">**Questo è il valore predefinito.**</span><span class="sxs-lookup"><span data-stu-id="ae820-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="ae820-122">1</span><span class="sxs-lookup"><span data-stu-id="ae820-122">1</span></span> | <span data-ttu-id="ae820-123">Il qualificatore viene propagato alle istanze.</span><span class="sxs-lookup"><span data-stu-id="ae820-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="ae820-124">2</span><span class="sxs-lookup"><span data-stu-id="ae820-124">2</span></span> | <span data-ttu-id="ae820-125">Il qualificatore viene propagato alle classi derivate.</span><span class="sxs-lookup"><span data-stu-id="ae820-125">The qualifier is propagated to derived classes.</span></span> |
| <span data-ttu-id="ae820-126">' WBEM_FLAVOR_NOT_OVERRIDABLE</span><span class="sxs-lookup"><span data-stu-id="ae820-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span></span> | <span data-ttu-id="ae820-127">0x10</span><span class="sxs-lookup"><span data-stu-id="ae820-127">0x10</span></span> | <span data-ttu-id="ae820-128">Il qualificatore non può essere sottoposto a override in una classe o in un'istanza derivata.</span><span class="sxs-lookup"><span data-stu-id="ae820-128">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| <span data-ttu-id="ae820-129">' WBEM_FLAVOR_AMENDED</span><span class="sxs-lookup"><span data-stu-id="ae820-129">\`WBEM_FLAVOR_AMENDED</span></span> | <span data-ttu-id="ae820-130">0x80</span><span class="sxs-lookup"><span data-stu-id="ae820-130">0x80</span></span> | <span data-ttu-id="ae820-131">Il qualificatore è localizzato.</span><span class="sxs-lookup"><span data-stu-id="ae820-131">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="ae820-132">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="ae820-132">Return value</span></span>

<span data-ttu-id="ae820-133">I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:</span><span class="sxs-lookup"><span data-stu-id="ae820-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ae820-134">Costante</span><span class="sxs-lookup"><span data-stu-id="ae820-134">Constant</span></span>  |<span data-ttu-id="ae820-135">Valore</span><span class="sxs-lookup"><span data-stu-id="ae820-135">Value</span></span>  |<span data-ttu-id="ae820-136">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae820-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="ae820-137">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="ae820-137">0x8004101f</span></span> | <span data-ttu-id="ae820-138">Si è verificato un tentativo non valido per specificare il **chiave** qualificatore su una proprietà che non può essere una chiave.</span><span class="sxs-lookup"><span data-stu-id="ae820-138">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="ae820-139">Le chiavi sono specificate om c; definizione ass per un oggetto e non possono essere alterate per ogni istanza.</span><span class="sxs-lookup"><span data-stu-id="ae820-139">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ae820-140">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ae820-140">0x80041008</span></span> | <span data-ttu-id="ae820-141">Un parametro non è valido.</span><span class="sxs-lookup"><span data-stu-id="ae820-141">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="ae820-142">0x80041029</span><span class="sxs-lookup"><span data-stu-id="ae820-142">0x80041029</span></span> | <span data-ttu-id="ae820-143">Il `pVal` parametro non è di un tipo di qualificatore valido.</span><span class="sxs-lookup"><span data-stu-id="ae820-143">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="ae820-144">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="ae820-144">0x8004101a</span></span> | <span data-ttu-id="ae820-145">Non è possibile chiamare il `QualifierSet_Put` metodo sul qualificatore perché l'oggetto proprietario non consente sostituzioni.</span><span class="sxs-lookup"><span data-stu-id="ae820-145">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="ae820-146">0</span><span class="sxs-lookup"><span data-stu-id="ae820-146">0</span></span> | <span data-ttu-id="ae820-147">La chiamata di funzione è stata completata.</span><span class="sxs-lookup"><span data-stu-id="ae820-147">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ae820-148">Note</span><span class="sxs-lookup"><span data-stu-id="ae820-148">Remarks</span></span>

<span data-ttu-id="ae820-149">Questa funzione esegue il wrapping di una chiamata al [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) metodo.</span><span class="sxs-lookup"><span data-stu-id="ae820-149">This function wraps a call to the [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="ae820-150">Requisiti</span><span class="sxs-lookup"><span data-stu-id="ae820-150">Requirements</span></span>  
 <span data-ttu-id="ae820-151">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ae820-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae820-152">**Intestazione:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ae820-152">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ae820-153">**Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ae820-153">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae820-154">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ae820-154">See also</span></span>  
[<span data-ttu-id="ae820-155">WMI e i contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="ae820-155">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
