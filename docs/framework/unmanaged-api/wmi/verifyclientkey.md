---
title: VerifyClientKey (riferimento all'API non gestita)
description: La funzione VerifyClientKey garantisce la sicurezza corretta della chiave client.
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
ms.openlocfilehash: ebb794240494deb0c831b50e95461ec52017a215
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176708"
---
# <a name="verifyclientkey-function"></a>VerifyClientKey (funzione)
Verifica che la chiave client includa la sicurezza corretta.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
LONG VerifyClientKey();
```  

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito `ERROR_SUCCESS` positivo, il valore restituito è (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero definito in *WinError.h*.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.def  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
