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
in Tipo di contatore. Per un elenco dei tipi di contatore, vedere [tipi di contatori delle prestazioni WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType`può essere qualsiasi tipo di contatore, `PERF_LARGE_RAW_FRACTION` ad `PERF_LARGE_RAW_BASE`eccezione di e. 

`dwFormat`\
in Formato in cui convertire i dati delle prestazioni non elaborati. Può essere uno dei valori seguenti:

|Costante  |Valore  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Restituisce il valore calcolato come valore a virgola mobile a precisione doppia. | 
| `PDH_FMT_LARGE` | 0x00000400 | Restituisce il valore calcolato come intero a 64 bit. |
| `PDH_FMT_LONG` | 0x00000100 | Restituisce il valore calcolato come intero a 32 bit. |

Uno dei valori precedenti può essere ORed con uno dei flag di ridimensionamento seguenti:

|Costante  |Value  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Non applicare i fattori di scala del contatore. |
| `PDH_FMT_1000` | 0x00002000 | Moltiplicare il valore finale di 1.000. | 

`pTimeBase`\
in Puntatore alla base temporale, se necessario per la conversione del formato. Se le informazioni di base sull'ora non sono necessarie per la conversione del formato, il valore di questo parametro viene ignorato.

`pRawValue1`[in] puntatore a una [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) struttura che rappresenta un valore di prestazioni non elaborate.

`pRawValue2`\
in Puntatore a una [`PDH_RAW_COUNTER`](/windows/win32/api/pdh/ns-pdh-pdh_raw_counter) struttura che rappresenta un secondo valore di prestazioni non elaborate. Se non è necessario un secondo valore delle prestazioni non elaborate, questo `null`parametro deve essere.

`pFmtValue`\
out Puntatore a una [`PDH_FMT_COUNTERVALUE`](/windows/win32/api/pdh/ns-pdh-pdh_fmt_countervalue) struttura che riceve il valore di prestazioni formattato.

## <a name="return-value"></a>Valore restituito

Questa funzione restituisce i valori seguenti:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La chiamata di funzione ha avuto esito positivo. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Argomento obbligatorio mancante o non corretto. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | L'handle non è un oggetto PDH valido. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata alla funzione [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) .

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

 **Libreria** PerfCounter.dll

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
