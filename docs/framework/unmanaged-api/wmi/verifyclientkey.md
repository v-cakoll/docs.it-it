---
title: Funzione VerifyClientKey (riferimenti alle API non gestite)
description: La funzione VerifyClientKey garantisce che la chiave client disponga della sicurezza corretta.
ms.date: 11/06/2017
api_name:
- VerifyClientKey
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- VerifyClientKey
helpviewer_keywords:
- VerifyClientKey function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 0a0680651eb192e2798ede00048599c5130e63f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107352"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey (funzione)
Verifica che la chiave client includa la sicurezza corretta.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
LONG VerifyClientKey(); 
```  

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito positivo, il valore restituito è `ERROR_SUCCESS` (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito in *Winerror. h*.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. def  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
