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
ms.openlocfilehash: 90af7d01d78cf74cbb304e3b987d5fe58e23f76e
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2018
ms.locfileid: "50196700"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="fd4be-103">FormatFromRawValue (funzione)</span><span class="sxs-lookup"><span data-stu-id="fd4be-103">FormatFromRawValue function</span></span>
<span data-ttu-id="fd4be-104">Converte un valore di dati sulle prestazioni non elaborati nel formato specificato o due valori di dati sulle prestazioni non elaborati se la conversione del formato è basata sul tempo.</span><span class="sxs-lookup"><span data-stu-id="fd4be-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fd4be-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="fd4be-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="fd4be-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="fd4be-106">Parameters</span></span>

`dwCounterType`  
<span data-ttu-id="fd4be-107">[in] Il tipo di contatore.</span><span class="sxs-lookup"><span data-stu-id="fd4be-107">[in] The counter type.</span></span> <span data-ttu-id="fd4be-108">Per un elenco di tipi di contatori, vedere [tipi di contatore delle prestazioni WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="fd4be-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="fd4be-109">`dwCounterType` può essere qualsiasi tipo di contatore, ad eccezione di `PERF_LARGE_RAW_FRACTION` e `PERF_LARGE_RAW_BASE`.</span><span class="sxs-lookup"><span data-stu-id="fd4be-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`  
<span data-ttu-id="fd4be-110">[in] Il formato nel quale convertire i dati sulle prestazioni non elaborati.</span><span class="sxs-lookup"><span data-stu-id="fd4be-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="fd4be-111">Può essere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd4be-111">It can be one of the following values:</span></span>

|<span data-ttu-id="fd4be-112">Costante</span><span class="sxs-lookup"><span data-stu-id="fd4be-112">Constant</span></span>  |<span data-ttu-id="fd4be-113">Valore</span><span class="sxs-lookup"><span data-stu-id="fd4be-113">Value</span></span>  |<span data-ttu-id="fd4be-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd4be-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="fd4be-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="fd4be-115">0x00000200</span></span> | <span data-ttu-id="fd4be-116">Restituisce il valore calcolato come un valore a virgola mobile a precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="fd4be-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="fd4be-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="fd4be-117">0x00000400</span></span> | <span data-ttu-id="fd4be-118">Restituisce il valore calcolato come intero a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="fd4be-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="fd4be-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="fd4be-119">0x00000100</span></span> | <span data-ttu-id="fd4be-120">Restituisce il valore calcolato come intero a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="fd4be-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="fd4be-121">Uno dei valori precedenti può essere introdotte con uno dei flag di ridimensionamento seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd4be-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="fd4be-122">Costante</span><span class="sxs-lookup"><span data-stu-id="fd4be-122">Constant</span></span>  |<span data-ttu-id="fd4be-123">Valore</span><span class="sxs-lookup"><span data-stu-id="fd4be-123">Value</span></span>  |<span data-ttu-id="fd4be-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd4be-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="fd4be-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="fd4be-125">0x00001000</span></span> | <span data-ttu-id="fd4be-126">Non si applicano i fattori di scala del contatore.</span><span class="sxs-lookup"><span data-stu-id="fd4be-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="fd4be-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="fd4be-127">0x00002000</span></span> | <span data-ttu-id="fd4be-128">Moltiplicare il valore finale per 1.000.</span><span class="sxs-lookup"><span data-stu-id="fd4be-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`  
<span data-ttu-id="fd4be-129">[in] Puntatore alla base di tempo, se necessario per la conversione di formato.</span><span class="sxs-lookup"><span data-stu-id="fd4be-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="fd4be-130">Se le informazioni di base di tempo non sono necessarie per la conversione di formato, il valore di questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="fd4be-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="fd4be-131">`pRawValue1` [in] Un puntatore a un [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) struttura che rappresenta un valore delle prestazioni raw.</span><span class="sxs-lookup"><span data-stu-id="fd4be-131">`pRawValue1` [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a raw performance value.</span></span>

<span data-ttu-id="fd4be-132">`pRawValue2` [in] Un puntatore a un [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) struttura che rappresenta un secondo valore sulle prestazioni non elaborati.</span><span class="sxs-lookup"><span data-stu-id="fd4be-132">`pRawValue2` [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="fd4be-133">Se un secondo valore delle prestazioni raw non è necessario, questo parametro deve essere `null`.</span><span class="sxs-lookup"><span data-stu-id="fd4be-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

<span data-ttu-id="fd4be-134">`pFmtValue` [out] Un puntatore a un [ `PDH_FMT_COUNTERVALUE` ](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) struttura che riceve il valore formattato le prestazioni.</span><span class="sxs-lookup"><span data-stu-id="fd4be-134">`pFmtValue` [out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd4be-135">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="fd4be-135">Return value</span></span>

<span data-ttu-id="fd4be-136">I valori seguenti vengono restituiti da questa funzione:</span><span class="sxs-lookup"><span data-stu-id="fd4be-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="fd4be-137">Costante</span><span class="sxs-lookup"><span data-stu-id="fd4be-137">Constant</span></span>  |<span data-ttu-id="fd4be-138">Valore</span><span class="sxs-lookup"><span data-stu-id="fd4be-138">Value</span></span>  |<span data-ttu-id="fd4be-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fd4be-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="fd4be-140">0</span><span class="sxs-lookup"><span data-stu-id="fd4be-140">0</span></span> | <span data-ttu-id="fd4be-141">La chiamata di funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="fd4be-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="fd4be-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="fd4be-142">0xC0000BBD</span></span> | <span data-ttu-id="fd4be-143">Un argomento obbligatorio è mancante o non corretto.</span><span class="sxs-lookup"><span data-stu-id="fd4be-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="fd4be-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="fd4be-144">0xC0000BBC</span></span> | <span data-ttu-id="fd4be-145">L'handle non è un oggetto PDH valido.</span><span class="sxs-lookup"><span data-stu-id="fd4be-145">The handle is not a valid PDH object.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="fd4be-146">Note</span><span class="sxs-lookup"><span data-stu-id="fd4be-146">Remarks</span></span>

<span data-ttu-id="fd4be-147">Questa funzione esegue il wrapping di una chiamata per il [FormatFromRawValue](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms231047%28v=vs.85%29) (funzione).</span><span class="sxs-lookup"><span data-stu-id="fd4be-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.0/ms231047%28v=vs.85%29) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd4be-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="fd4be-148">Requirements</span></span>  
 <span data-ttu-id="fd4be-149">**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd4be-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd4be-150">**Libreria:** PerfCounter. dll</span><span class="sxs-lookup"><span data-stu-id="fd4be-150">**Library:** PerfCounter.dll</span></span>  
  
 <span data-ttu-id="fd4be-151">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fd4be-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd4be-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fd4be-152">See also</span></span>  
[<span data-ttu-id="fd4be-153">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="fd4be-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
