---
title: Funzione di sicurezza (riferimenti alle API non gestite)
description: La funzione di sicurezza recupera il token di rappresentazione del thread corrente.
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
ms.openlocfilehash: 6d27779bcfc97e1c4156b8782896e83d4754491b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120221"
---
# <a name="setsecurity-function"></a>Funzione di sicurezza

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
out Quando la funzione restituisce un valore, contiene un puntatore a un `boolean` che indica se il token deve essere reimpostato chiamando la funzione [ResetSecurity](resetsecurity.md) .

`token`\
out Quando la funzione restituisce un valore, contiene un puntatore all'handle del token di rappresentazione associato al thread corrente. Il valore può essere `null` se al thread corrente non è associato alcun token. 

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito positivo, il valore restituito è `S_OK` (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero. Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils. idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
