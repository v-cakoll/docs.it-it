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
ms.openlocfilehash: 44a84b03c85cc1332c07ffbaf53187b7f01d0236
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609048"
---
# <a name="formatfromrawvalue-function"></a>Funzione FormatFromRawValue
Converte un valore di dati sulle prestazioni non elaborati nel formato specificato o due valori di dati sulle prestazioni non elaborati se la conversione del formato è basata sul tempo. 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

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

## <a name="parameters"></a>Parametri

`dwCounterType`\
[in] Il tipo di contatore. Per un elenco di tipi di contatori, vedere [tipi di contatore delle prestazioni WMI](/windows/desktop/WmiSdk/wmi-performance-counter-types). `dwCounterType` può essere qualsiasi tipo di contatore, ad eccezione di `PERF_LARGE_RAW_FRACTION` e `PERF_LARGE_RAW_BASE`. 

`dwFormat`\
[in] Il formato nel quale convertire i dati sulle prestazioni non elaborati. Può essere uno dei valori seguenti:

|Costante  |Value  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Restituisce il valore calcolato come un valore a virgola mobile a precisione doppia. | 
| `PDH_FMT_LARGE` | 0x00000400 | Restituisce il valore calcolato come intero a 64 bit. |
| `PDH_FMT_LONG` | 0x00000100 | Restituisce il valore calcolato come intero a 32 bit. |

Uno dei valori precedenti può essere introdotte con uno dei flag di ridimensionamento seguenti:

|Costante  |Value  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Non si applicano i fattori di scala del contatore. |
| `PDH_FMT_1000` | 0x00002000 | Moltiplicare il valore finale per 1.000. | 

`pTimeBase`\
[in] Puntatore alla base di tempo, se necessario per la conversione di formato. Se le informazioni di base di tempo non sono necessarie per la conversione di formato, il valore di questo parametro viene ignorato.

`pRawValue1`\ [in] puntatore a un [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) struttura che rappresenta un valore delle prestazioni raw.

`pRawValue2`\
[in] Un puntatore a un [ `PDH_RAW_COUNTER` ](/windows/desktop/api/pdh/ns-pdh-_pdh_raw_counter) struttura che rappresenta un secondo valore sulle prestazioni non elaborati. Se un secondo valore delle prestazioni raw non è necessario, questo parametro deve essere `null`.

`pFmtValue`\
[out] Un puntatore a un [ `PDH_FMT_COUNTERVALUE` ](/windows/desktop/api/pdh/ns-pdh-_pdh_fmt_countervalue) struttura che riceve il valore formattato le prestazioni.

## <a name="return-value"></a>Valore restituito

I valori seguenti vengono restituiti da questa funzione:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La chiamata di funzione ha esito positivo. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Un argomento obbligatorio è mancante o non corretto. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | L'handle non è un oggetto PDH valido. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [FormatFromRawValue](https://docs.microsoft.com/previous-versions/ms231047(v=vs.85)) (funzione).

## <a name="requirements"></a>Requisiti

 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Libreria:** PerfCounter.dll

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
