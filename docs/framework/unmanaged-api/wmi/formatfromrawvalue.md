---
title: Funzione FormatFromRawValue (riferimenti alle API non gestite)
description: La funzione FormatFromRawValue converte i dati delle prestazioni non elaborati in un formato specificato.
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
ms.openlocfilehash: 65a6d9eab9708f762d14e5361697b85ffb73f54a
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798639"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="c8590-103">Funzione FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="c8590-103">FormatFromRawValue function</span></span>
<span data-ttu-id="c8590-104">Converte un valore di dati sulle prestazioni non elaborati nel formato specificato o due valori di dati sulle prestazioni non elaborati se la conversione del formato è basata sul tempo.</span><span class="sxs-lookup"><span data-stu-id="c8590-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c8590-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="c8590-105">Syntax</span></span>

```cpp
int FormatFromRawValue (
   [in] uint                    dwCounterType, 
   [in] uint                    dwFormat, 
   [in] long*                   pTimeBase,
   [in] PDH_RAW_COUNTER*        pRawValue1,
   [in] PDH_RAW_COUNTER*        pRawValue2,
   [out] PDH_FMT_COUNTERVALUE*  pFmtValue
); 
```

## <a name="parameters"></a><span data-ttu-id="c8590-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="c8590-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="c8590-107">in Tipo di contatore.</span><span class="sxs-lookup"><span data-stu-id="c8590-107">[in] The counter type.</span></span> <span data-ttu-id="c8590-108">Per un elenco dei tipi di contatore, vedere [tipi di contatori delle prestazioni WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="c8590-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="c8590-109">`dwCounterType`può essere qualsiasi tipo di contatore, `PERF_LARGE_RAW_FRACTION` ad `PERF_LARGE_RAW_BASE`eccezione di e.</span><span class="sxs-lookup"><span data-stu-id="c8590-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span> 

`dwFormat`\
<span data-ttu-id="c8590-110">in Formato in cui convertire i dati delle prestazioni non elaborati.</span><span class="sxs-lookup"><span data-stu-id="c8590-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="c8590-111">Può essere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8590-111">It can be one of the following values:</span></span>

|<span data-ttu-id="c8590-112">Costante</span><span class="sxs-lookup"><span data-stu-id="c8590-112">Constant</span></span>  |<span data-ttu-id="c8590-113">Valore</span><span class="sxs-lookup"><span data-stu-id="c8590-113">Value</span></span>  |<span data-ttu-id="c8590-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8590-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="c8590-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="c8590-115">0x00000200</span></span> | <span data-ttu-id="c8590-116">Restituisce il valore calcolato come valore a virgola mobile a precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="c8590-116">Return the calculated value as a double-precision floating point value.</span></span> | 
| `PDH_FMT_LARGE` | <span data-ttu-id="c8590-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="c8590-117">0x00000400</span></span> | <span data-ttu-id="c8590-118">Restituisce il valore calcolato come intero a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="c8590-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="c8590-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="c8590-119">0x00000100</span></span> | <span data-ttu-id="c8590-120">Restituisce il valore calcolato come intero a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="c8590-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="c8590-121">Uno dei valori precedenti può essere ORed con uno dei flag di ridimensionamento seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8590-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="c8590-122">Costante</span><span class="sxs-lookup"><span data-stu-id="c8590-122">Constant</span></span>  |<span data-ttu-id="c8590-123">Value</span><span class="sxs-lookup"><span data-stu-id="c8590-123">Value</span></span>  |<span data-ttu-id="c8590-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8590-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="c8590-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="c8590-125">0x00001000</span></span> | <span data-ttu-id="c8590-126">Non applicare i fattori di scala del contatore.</span><span class="sxs-lookup"><span data-stu-id="c8590-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="c8590-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="c8590-127">0x00002000</span></span> | <span data-ttu-id="c8590-128">Moltiplicare il valore finale di 1.000.</span><span class="sxs-lookup"><span data-stu-id="c8590-128">Multiply the final value by 1,000.</span></span> | 

`pTimeBase`\
<span data-ttu-id="c8590-129">in Puntatore alla base temporale, se necessario per la conversione del formato.</span><span class="sxs-lookup"><span data-stu-id="c8590-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="c8590-130">Se le informazioni di base sull'ora non sono necessarie per la conversione del formato, il valore di questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="c8590-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

<span data-ttu-id="c8590-131">`pRawValue1`[in] puntatore a una [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) struttura che rappresenta un valore di prestazioni non elaborate.</span><span class="sxs-lookup"><span data-stu-id="c8590-131">`pRawValue1`\ [in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="c8590-132">in Puntatore a una [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) struttura che rappresenta un secondo valore di prestazioni non elaborate.</span><span class="sxs-lookup"><span data-stu-id="c8590-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="c8590-133">Se non è necessario un secondo valore delle prestazioni non elaborate, questo `null`parametro deve essere.</span><span class="sxs-lookup"><span data-stu-id="c8590-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="c8590-134">out Puntatore a una [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) struttura che riceve il valore di prestazioni formattato.</span><span class="sxs-lookup"><span data-stu-id="c8590-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="c8590-135">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="c8590-135">Return value</span></span>

<span data-ttu-id="c8590-136">Questa funzione restituisce i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="c8590-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="c8590-137">Costante</span><span class="sxs-lookup"><span data-stu-id="c8590-137">Constant</span></span>  |<span data-ttu-id="c8590-138">Value</span><span class="sxs-lookup"><span data-stu-id="c8590-138">Value</span></span>  |<span data-ttu-id="c8590-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c8590-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="c8590-140">0</span><span class="sxs-lookup"><span data-stu-id="c8590-140">0</span></span> | <span data-ttu-id="c8590-141">La chiamata di funzione ha avuto esito positivo.</span><span class="sxs-lookup"><span data-stu-id="c8590-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="c8590-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="c8590-142">0xC0000BBD</span></span> | <span data-ttu-id="c8590-143">Argomento obbligatorio mancante o non corretto.</span><span class="sxs-lookup"><span data-stu-id="c8590-143">A required argument is missing or incorrect.</span></span> | 
| `PDH_INVALID_HANDLE` | <span data-ttu-id="c8590-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="c8590-144">0xC0000BBC</span></span> | <span data-ttu-id="c8590-145">L'handle non è un oggetto PDH valido.</span><span class="sxs-lookup"><span data-stu-id="c8590-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c8590-146">Note</span><span class="sxs-lookup"><span data-stu-id="c8590-146">Remarks</span></span>

<span data-ttu-id="c8590-147">Questa funzione esegue il wrapping di una chiamata alla funzione [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) .</span><span class="sxs-lookup"><span data-stu-id="c8590-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="c8590-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="c8590-148">Requirements</span></span>

 <span data-ttu-id="c8590-149">**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8590-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="c8590-150">**Libreria** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="c8590-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="c8590-151">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c8590-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c8590-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c8590-152">See also</span></span>

- [<span data-ttu-id="c8590-153">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="c8590-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
