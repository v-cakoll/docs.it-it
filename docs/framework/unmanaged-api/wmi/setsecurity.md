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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94c76213acb66116105d181e9961a33976047ee7
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798246"
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
out Quando la funzione restituisce un valore, contiene un puntatore `boolean` a un valore che indica se il token deve essere reimpostato chiamando la funzione [ResetSecurity](resetsecurity.md) .

`token`\
out Quando la funzione restituisce un valore, contiene un puntatore all'handle del token di rappresentazione associato al thread corrente. Il valore può essere `null` se al thread corrente non è associato alcun token. 

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito positivo, il valore `S_OK` restituito è (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero. Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils. idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
