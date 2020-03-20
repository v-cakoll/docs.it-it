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
ms.openlocfilehash: 0a7c0b8387f0c8e2b6e2ade94f7efeede75bd758
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176838"
---
# <a name="formatfromrawvalue-function"></a><span data-ttu-id="5e351-103">Funzione FormatFromRawValue</span><span class="sxs-lookup"><span data-stu-id="5e351-103">FormatFromRawValue function</span></span>
<span data-ttu-id="5e351-104">Converte un valore di dati sulle prestazioni non elaborati nel formato specificato o due valori di dati sulle prestazioni non elaborati se la conversione del formato è basata sul tempo.</span><span class="sxs-lookup"><span data-stu-id="5e351-104">Converts one raw performance data value to the specified format, or two raw performance data values if the format conversion is time-based.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="5e351-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="5e351-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="5e351-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="5e351-106">Parameters</span></span>

`dwCounterType`\
<span data-ttu-id="5e351-107">[in] Tipo di contatore.</span><span class="sxs-lookup"><span data-stu-id="5e351-107">[in] The counter type.</span></span> <span data-ttu-id="5e351-108">Per un elenco dei tipi di contatore, vedere [Tipi di contatori delle prestazioni WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span><span class="sxs-lookup"><span data-stu-id="5e351-108">For a list of counter types, see [WMI Performance Counter Types](/windows/desktop/WmiSdk/wmi-performance-counter-types).</span></span> <span data-ttu-id="5e351-109">`dwCounterType`può essere qualsiasi tipo `PERF_LARGE_RAW_FRACTION` `PERF_LARGE_RAW_BASE`di contatore ad eccezione di e .</span><span class="sxs-lookup"><span data-stu-id="5e351-109">`dwCounterType` can be any counter type except for `PERF_LARGE_RAW_FRACTION` and `PERF_LARGE_RAW_BASE`.</span></span>

`dwFormat`\
<span data-ttu-id="5e351-110">[in] Formato in cui convertire i dati non elaborati sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="5e351-110">[in] The format to which to convert the raw performance data.</span></span> <span data-ttu-id="5e351-111">Può essere uno dei valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e351-111">It can be one of the following values:</span></span>

|<span data-ttu-id="5e351-112">Costante</span><span class="sxs-lookup"><span data-stu-id="5e351-112">Constant</span></span>  |<span data-ttu-id="5e351-113">valore</span><span class="sxs-lookup"><span data-stu-id="5e351-113">Value</span></span>  |<span data-ttu-id="5e351-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e351-114">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |<span data-ttu-id="5e351-115">0x00000200</span><span class="sxs-lookup"><span data-stu-id="5e351-115">0x00000200</span></span> | <span data-ttu-id="5e351-116">Restituisce il valore calcolato come valore a virgola mobile e precisione doppia.</span><span class="sxs-lookup"><span data-stu-id="5e351-116">Return the calculated value as a double-precision floating point value.</span></span> |
| `PDH_FMT_LARGE` | <span data-ttu-id="5e351-117">0x00000400</span><span class="sxs-lookup"><span data-stu-id="5e351-117">0x00000400</span></span> | <span data-ttu-id="5e351-118">Restituisce il valore calcolato come numero intero a 64 bit.</span><span class="sxs-lookup"><span data-stu-id="5e351-118">Return the calculated value as a 64-bit integer.</span></span> |
| `PDH_FMT_LONG` | <span data-ttu-id="5e351-119">0x00000100</span><span class="sxs-lookup"><span data-stu-id="5e351-119">0x00000100</span></span> | <span data-ttu-id="5e351-120">Restituisce il valore calcolato come numero intero a 32 bit.</span><span class="sxs-lookup"><span data-stu-id="5e351-120">Return the calculated value as a 32-bit integer.</span></span> |

<span data-ttu-id="5e351-121">Uno dei valori precedenti può essere ORed con uno dei seguenti flag di ridimensionamento:</span><span class="sxs-lookup"><span data-stu-id="5e351-121">One of the previous values can be ORed with one of the following scaling flags:</span></span>

|<span data-ttu-id="5e351-122">Costante</span><span class="sxs-lookup"><span data-stu-id="5e351-122">Constant</span></span>  |<span data-ttu-id="5e351-123">valore</span><span class="sxs-lookup"><span data-stu-id="5e351-123">Value</span></span>  |<span data-ttu-id="5e351-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e351-124">Description</span></span> |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | <span data-ttu-id="5e351-125">0x00001000</span><span class="sxs-lookup"><span data-stu-id="5e351-125">0x00001000</span></span> | <span data-ttu-id="5e351-126">Non applicare i fattori di scala del contatore.</span><span class="sxs-lookup"><span data-stu-id="5e351-126">Do not apply the counter's scaling factors.</span></span> |
| `PDH_FMT_1000` | <span data-ttu-id="5e351-127">0x00002000</span><span class="sxs-lookup"><span data-stu-id="5e351-127">0x00002000</span></span> | <span data-ttu-id="5e351-128">Moltiplicare il valore finale per 1.000.</span><span class="sxs-lookup"><span data-stu-id="5e351-128">Multiply the final value by 1,000.</span></span> |

`pTimeBase`\
<span data-ttu-id="5e351-129">[in] Puntatore alla base temporale, se necessario per la conversione del formato.</span><span class="sxs-lookup"><span data-stu-id="5e351-129">[in] A pointer to the time base, if necessary for the format conversion.</span></span> <span data-ttu-id="5e351-130">Se le informazioni di base dell'ora non sono necessarie per la conversione del formato, il valore di questo parametro viene ignorato.</span><span class="sxs-lookup"><span data-stu-id="5e351-130">If time base information is not necessary for the format conversion, the value of this parameter is ignored.</span></span>

`pRawValue1`\
<span data-ttu-id="5e351-131">[in] Puntatore a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una struttura che rappresenta un valore delle prestazioni non elaborato.</span><span class="sxs-lookup"><span data-stu-id="5e351-131">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a raw performance value.</span></span>

`pRawValue2`\
<span data-ttu-id="5e351-132">[in] Puntatore a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una struttura che rappresenta un secondo valore di prestazioni non elaborato.</span><span class="sxs-lookup"><span data-stu-id="5e351-132">[in] A pointer to a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) structure that represents a second raw performance value.</span></span> <span data-ttu-id="5e351-133">Se non è necessario un secondo valore `null`delle prestazioni non elaborato, questo parametro deve essere .</span><span class="sxs-lookup"><span data-stu-id="5e351-133">If a second raw performance value is not necessary, this parameter should be `null`.</span></span>

`pFmtValue`\
<span data-ttu-id="5e351-134">[fuori] Puntatore a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) una struttura che riceve il valore delle prestazioni formattato.</span><span class="sxs-lookup"><span data-stu-id="5e351-134">[out] A pointer to a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) structure that receives the formatted performance value.</span></span>

## <a name="return-value"></a><span data-ttu-id="5e351-135">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="5e351-135">Return value</span></span>

<span data-ttu-id="5e351-136">Questa funzione restituisce i seguenti valori:</span><span class="sxs-lookup"><span data-stu-id="5e351-136">The following values are returned by this function:</span></span>

|<span data-ttu-id="5e351-137">Costante</span><span class="sxs-lookup"><span data-stu-id="5e351-137">Constant</span></span>  |<span data-ttu-id="5e351-138">valore</span><span class="sxs-lookup"><span data-stu-id="5e351-138">Value</span></span>  |<span data-ttu-id="5e351-139">Descrizione</span><span class="sxs-lookup"><span data-stu-id="5e351-139">Description</span></span>  |
|---------|---------|---------|
| `ERROR_SUCCESS` | <span data-ttu-id="5e351-140">0</span><span class="sxs-lookup"><span data-stu-id="5e351-140">0</span></span> | <span data-ttu-id="5e351-141">La chiamata di funzione ha esito positivo.</span><span class="sxs-lookup"><span data-stu-id="5e351-141">The function call is successful.</span></span> |
| `PDH_INVALID_ARGUMENT` | <span data-ttu-id="5e351-142">0xC0000BBD</span><span class="sxs-lookup"><span data-stu-id="5e351-142">0xC0000BBD</span></span> | <span data-ttu-id="5e351-143">Un argomento obbligatorio è mancante o non corretto.</span><span class="sxs-lookup"><span data-stu-id="5e351-143">A required argument is missing or incorrect.</span></span> |
| `PDH_INVALID_HANDLE` | <span data-ttu-id="5e351-144">0xC0000BBC</span><span class="sxs-lookup"><span data-stu-id="5e351-144">0xC0000BBC</span></span> | <span data-ttu-id="5e351-145">L'handle non è un oggetto PDH valido.</span><span class="sxs-lookup"><span data-stu-id="5e351-145">The handle is not a valid PDH object.</span></span> |

## <a name="remarks"></a><span data-ttu-id="5e351-146">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="5e351-146">Remarks</span></span>

<span data-ttu-id="5e351-147">Questa funzione esegue il wrapping di una chiamata alla funzione [FormatFromRawValue.This](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function wraps a call to the FormatFromRawValue function.</span><span class="sxs-lookup"><span data-stu-id="5e351-147">This function wraps a call to the [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="5e351-148">Requisiti</span><span class="sxs-lookup"><span data-stu-id="5e351-148">Requirements</span></span>

 <span data-ttu-id="5e351-149">**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e351-149">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="5e351-150">**Biblioteca:** PerfCounter.dll</span><span class="sxs-lookup"><span data-stu-id="5e351-150">**Library:** PerfCounter.dll</span></span>

 <span data-ttu-id="5e351-151">**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5e351-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="5e351-152">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5e351-152">See also</span></span>

- [<span data-ttu-id="5e351-153">WMI e contatori delle prestazioni (riferimenti alle API non gestite)</span><span class="sxs-lookup"><span data-stu-id="5e351-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
