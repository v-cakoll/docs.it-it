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
# <a name="formatfromrawvalue-function"></a>Funzione FormatFromRawValue
Converte un valore di dati sulle prestazioni non elaborati nel formato specificato o due valori di dati sulle prestazioni non elaborati se la conversione del formato è basata sul tempo.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

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

## <a name="parameters"></a>Parametri

`dwCounterType`\
[in] Tipo di contatore. Per un elenco dei tipi di contatore, vedere [Tipi di contatori delle prestazioni WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType`può essere qualsiasi tipo `PERF_LARGE_RAW_FRACTION` `PERF_LARGE_RAW_BASE`di contatore ad eccezione di e .

`dwFormat`\
[in] Formato in cui convertire i dati non elaborati sulle prestazioni. Può essere uno dei valori seguenti:

|Costante  |valore  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Restituisce il valore calcolato come valore a virgola mobile e precisione doppia. |
| `PDH_FMT_LARGE` | 0x00000400 | Restituisce il valore calcolato come numero intero a 64 bit. |
| `PDH_FMT_LONG` | 0x00000100 | Restituisce il valore calcolato come numero intero a 32 bit. |

Uno dei valori precedenti può essere ORed con uno dei seguenti flag di ridimensionamento:

|Costante  |valore  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Non applicare i fattori di scala del contatore. |
| `PDH_FMT_1000` | 0x00002000 | Moltiplicare il valore finale per 1.000. |

`pTimeBase`\
[in] Puntatore alla base temporale, se necessario per la conversione del formato. Se le informazioni di base dell'ora non sono necessarie per la conversione del formato, il valore di questo parametro viene ignorato.

`pRawValue1`\
[in] Puntatore a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una struttura che rappresenta un valore delle prestazioni non elaborato.

`pRawValue2`\
[in] Puntatore a [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) una struttura che rappresenta un secondo valore di prestazioni non elaborato. Se non è necessario un secondo valore `null`delle prestazioni non elaborato, questo parametro deve essere .

`pFmtValue`\
[fuori] Puntatore a [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) una struttura che riceve il valore delle prestazioni formattato.

## <a name="return-value"></a>Valore restituito

Questa funzione restituisce i seguenti valori:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La chiamata di funzione ha esito positivo. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Un argomento obbligatorio è mancante o non corretto. |
| `PDH_INVALID_HANDLE` | 0xC0000BBC | L'handle non è un oggetto PDH valido. |

## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata alla funzione [FormatFromRawValue.This](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) function wraps a call to the FormatFromRawValue function.

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Biblioteca:** PerfCounter.dll

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
