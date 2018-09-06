---
title: Funzione FormatFromRawValue (riferimenti alle API non gestite)
description: La funzione FormatFromRawValue converte i dati sulle prestazioni non elaborati in un formato specificato.
ms.date: 11/21/2017
api_name:
- FormatFromRawValue
api_location:
- PerfCounter.dll
api_type:
- DLLExport
f1_keywords:
- FormatFromRawValue
helpviewer_keywords:
- FormatFromRawValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 95ef445d41672c5c2895bd7115afb6a73a57e8f9
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779919"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="07a1c-103">FormatFromRawValue (funzione)</span><span class="sxs-lookup"><span data-stu-id="07a1c-103">FormatFromRawValue function</span></span>
<span data-ttu-id="07a1c-104">Converte un valore di dati sulle prestazioni non elaborati nel formato specificato o due valori di dati sulle prestazioni non elaborati se la conversione del formato è basata sul tempo.</span><span class="sxs-lookup"><span data-stu-id="07a1c-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="07a1c-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="07a1c-105">Syntax</span></span>  
  
```  
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```  

## <a name="parameters"></a><span data-ttu-id="07a1c-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="07a1c-106">Parameters</span></span>

`dwCounterType`  
<span data-ttu-id="07a1c-107">[in] Il tipo di contatore.</span><span class="sxs-lookup"><span data-stu-id="07a1c-107">[in] The counter type.</span></span> <span data-ttu-id="07a1c-108">Per un elenco di tipi di contatori, vedere [tipi di contatore delle prestazioni WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="07a1c-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="07a1c-109">`dwCounterType` può essere qualsiasi tipo di contatore, ad eccezione di `PERF_LARGE_RAW_FRACTION` e `PERF_LARGE_RAW_BASE`.</span><span class="sxs-lookup"><span data-stu-id="07a1c-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`  
<span data-ttu-id="07a1c-110">[in] Il formato nel quale convertire i dati sulle prestazioni non elaborati.</span><span class="sxs-lookup"><span data-stu-id="07a1c-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="07a1c-111">Può essere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="07a1c-111">It can be one of the following values:</span></span>

|<span data-ttu-id="07a1c-112">Costante</span><span class="sxs-lookup"><span data-stu-id="07a1c-112">Constant</span></span>  |<span data-ttu-id="07a1c-113">Valore</span><span class="sxs-lookup"><span data-stu-id="07a1c-113">Value</span></span>  |<span data-ttu-id="07a1c-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07a1c-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="07a1c-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="07a1c-115">0x00000200</span></span> | <span data-ttu-id="07a1c-116">Restituisce il valore calcolato come un valore a virgola mobile a precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="07a1c-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="07a1c-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="07a1c-117">0x00000400</span></span> | <span data-ttu-id="07a1c-118">Restituisce il valore calcolato come intero a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="07a1c-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="07a1c-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="07a1c-119">0x00000100</span></span> | <span data-ttu-id="07a1c-120">Restituisce il valore calcolato come intero a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="07a1c-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="07a1c-121">Uno dei valori precedenti può essere introdotte con uno dei flag di ridimensionamento seguenti:</span><span class="sxs-lookup"><span data-stu-id="07a1c-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="07a1c-122">Costante</span><span class="sxs-lookup"><span data-stu-id="07a1c-122">Constant</span></span>  |<span data-ttu-id="07a1c-123">Valore</span><span class="sxs-lookup"><span data-stu-id="07a1c-123">Value</span></span>  |<span data-ttu-id="07a1c-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07a1c-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="07a1c-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="07a1c-125">0x00001000</span></span> | <span data-ttu-id="07a1c-126">Non si applicano i fattori di scala del contatore.</span><span class="sxs-lookup"><span data-stu-id="07a1c-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="07a1c-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="07a1c-127">0x00002000</span></span> | <span data-ttu-id="07a1c-128">Moltiplicare il valore finale per 1.000.</span><span class="sxs-lookup"><span data-stu-id="07a1c-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`  
<span data-ttu-id="07a1c-129">[in] Puntatore alla base di tempo, se necessario per la conversione di formato.</span><span class="sxs-lookup"><span data-stu-id="07a1c-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="07a1c-130">Se le informazioni di base di tempo non sono necessarie per la conversione di formato, il valore di questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="07a1c-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="07a1c-131">`pRawValue1` [in] Un puntatore a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) struttura che rappresenta un valore delle prestazioni raw.</span><span class="sxs-lookup"><span data-stu-id="07a1c-131">`pRawValue1` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a raw performance value.</span></span>

<span data-ttu-id="07a1c-132">`pRawValue2` [in] Un puntatore a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) struttura che rappresenta un secondo valore sulle prestazioni non elaborati.</span><span class="sxs-lookup"><span data-stu-id="07a1c-132">`pRawValue2` [in] A pointer to a [`PDH_RAW_COUNTER`](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) structure that represents a second raw performance value.</span></span> <span data-ttu-id="07a1c-133">Se un secondo valore delle prestazioni raw non è necessario, questo parametro deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="07a1c-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

<span data-ttu-id="07a1c-134">`pFmtValue` [out] Un puntatore a un [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) struttura che riceve il valore formattato le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="07a1c-134">`pFmtValue` [out] A pointer to a [`PDH_FMT_COUNTERVALUE`](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="07a1c-135">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="07a1c-135">Return value</span></span>

<span data-ttu-id="07a1c-136">I valori seguenti vengono restituiti da questa funzione:</span><span class="sxs-lookup"><span data-stu-id="07a1c-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="07a1c-137">Costante</span><span class="sxs-lookup"><span data-stu-id="07a1c-137">Constant</span></span>  |<span data-ttu-id="07a1c-138">Valore</span><span class="sxs-lookup"><span data-stu-id="07a1c-138">Value</span></span>  |<span data-ttu-id="07a1c-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="07a1c-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="07a1c-140">0</span><span class="sxs-lookup"><span data-stu-id="07a1c-140">0</span></span> | <span data-ttu-id="07a1c-141">La chiamata di funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="07a1c-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="07a1c-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="07a1c-142">0xC0000BBD</span></span> | <span data-ttu-id="07a1c-143">Un argomento obbligatorio è mancante o non corretto.</span><span class="sxs-lookup"><span data-stu-id="07a1c-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="07a1c-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="07a1c-144">0xC0000BBC</span></span> | <span data-ttu-id="07a1c-145">L'handle non è un oggetto PDH valido.</span><span class="sxs-lookup"><span data-stu-id="07a1c-145">The handle is not a valid PDH object.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="07a1c-146">Note</span><span class="sxs-lookup"><span data-stu-id="07a1c-146">Remarks</span></span>

<span data-ttu-id="07a1c-147">Questa funzione esegue il wrapping di una chiamata per il [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) (funzione).</span><span class="sxs-lookup"><span data-stu-id="07a1c-147">This function wraps a call to the [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="07a1c-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="07a1c-148">Requirements</span></span>  
 <span data-ttu-id="07a1c-149">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07a1c-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07a1c-150">**Libreria:** PerfCounter. dll</span><span class="sxs-lookup"><span data-stu-id="07a1c-150">**Library:** PerfCounter.dll</span></span>  
  
 <span data-ttu-id="07a1c-151">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="07a1c-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07a1c-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="07a1c-152">See also</span></span>  
[<span data-ttu-id="07a1c-153">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="07a1c-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
