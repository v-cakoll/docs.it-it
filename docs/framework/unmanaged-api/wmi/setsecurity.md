---
title: SetSecurity function (Unmanaged API Reference)
description: La funzione SetSecurity recupera il token di rappresentazione del thread corrente.
ms.date: 11/06/2017
api_name:
- SetSecurity
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SetSecurity
helpviewer_keywords:
- SetSecurity function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 809f6a95fdd6854b3a591b496877838c48d52199
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176734"
---
# <a name="setsecurity-function"></a>Funzione SetSecurity

Recupera il token di rappresentazione associato al thread corrente.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT SetSecurity (
   [out] boolean* pNeedToReset,
   [out] HANDLE* pCurrentThreadToken
);
```

## <a name="parameters"></a>Parametri

`pNeedToReset`\
[fuori] Quando la funzione restituisce, `boolean` contiene un puntatore a un che indica se il token deve essere reimpostato chiamando il [ResetSecurity](resetsecurity.md) funzione.

`token`\
[fuori] Quando la funzione restituisce, contiene un puntatore all'handle del token di rappresentazione associato al thread corrente. Il valore `null` può essere se non è presente alcun token associato al thread corrente.

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito `S_OK` positivo, il valore restituito è (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero. Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo.To](geterrorinfo.md) get extended error information, call the GetErrorInfo function.

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils.idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
