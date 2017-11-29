---
title: Funzione FormatFromRawValue (riferimenti alle API non gestite)
description: La funzione FormatFromRawValue converte i dati sulle prestazioni non elaborati in un formato specificato.
ms.date: 11/21/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: FormatFromRawValue
api_location: PerfCounter.dll
api_type: DLLExport
f1_keywords: FormatFromRawValue
helpviewer_keywords: FormatFromRawValue function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c01db47b5362d7048e2e5ecd1b63acfe03eff860
ms.sourcegitcommit: 43c656811dd38a66a6672084c65d10c0cbbf2015
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2017
---
# <a name="formatfromrawvalue-function"></a>FormatFromRawValue (funzione)
Converte un valore di dati delle prestazioni non elaborati nel formato specificato o due valori di tali dati se la conversione di formato è basato sul tempo.   
  
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

`dwCounterType`  
[in] Il tipo di contatore. Per un elenco di tipi di contatori, vedere [tipi di contatori delle prestazioni WMI](https://msdn.microsoft.com/library/aa394569(v=vs.85).aspx). `dwCounterType`può essere qualsiasi tipo di contatore, ad eccezione di `PERF_LARGE_RAW_FRACTION` e `PERF_LARGE_RAW_BASE`. 

`dwFormat`  
[in] Il formato nel quale convertire i dati sulle prestazioni non elaborati. Può essere uno dei valori seguenti:

|Costante  |Valore  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_DOUBLE` |0x00000200 | Restituisce il valore calcolato come valore a virgola mobile a precisione doppia. | 
| `PDH_FMT_LARGE` | 0x00000400 | Restituisce il valore calcolato come intero a 64 bit. |
| `PDH_FMT_LONG` | 0x00000100 | Restituisce il valore calcolato come intero a 32 bit. |

Può essere uno dei valori precedenti dall'operatore OR con uno dei flag di scala seguenti:

|Costante  |Valore  |Descrizione |
|---------|---------|---------|
| `PDH_FMT_NOSCALE` | 0x00001000 | Non si applicano i fattori di scala del contatore. |
| `PDH_FMT_1000` | 0x00002000 | Moltiplicare il valore finale per 1.000. | 

`pTimeBase`  
[in] Puntatore alla base di tempo, se necessario per la conversione di formato. Se le informazioni di base di ora non sono necessarie per la conversione di formato, il valore di questo parametro viene ignorato.

`pRawValue1`[in] Un puntatore a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) struttura che rappresenta un valore non elaborato delle prestazioni.

`pRawValue2`[in] Un puntatore a un [ `PDH_RAW_COUNTER` ](https://msdn.microsoft.com/library/windows/desktop/aa373060(v=vs.85).aspx) struttura che rappresenta un secondo valore sulle prestazioni non elaborati. Se un tale valore non è necessario, questo parametro deve essere `null`.

`pFmtValue`[out] Un puntatore a un [ `PDH_FMT_COUNTERVALUE` ](https://msdn.microsoft.com/library/windows/desktop/aa373050(v=vs.85).aspx) struttura che riceve il valore formattato delle prestazioni.

## <a name="return-value"></a>Valore restituito

Questa funzione, vengono restituiti i valori seguenti:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `ERROR_SUCCESS` | 0 | La chiamata di funzione ha esito positivo. |
| `PDH_INVALID_ARGUMENT` | 0xC0000BBD | Un argomento obbligatorio è mancante o non corretto. | 
| `PDH_INVALID_HANDLE` | 0xC0000BBC | L'handle non è un oggetto PDH valido. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [FormatFromRawValue](https://msdn.microsoft.com/library/ms231047(v=vs.85).aspx) (funzione).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Libreria:** PerfCounter  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
