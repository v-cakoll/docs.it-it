---
title: Funzione GetDemultiplexedStub (riferimenti alle API non gestite)
description: La funzione GetDemultiplexedStub crea un sink di server d'avanzamento oggetto per consentire a un client di ricevere chiamate asincrone dalla gestione di Windows.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a2d3885a4a9e54950909053ba18de5b1891e7edf
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798606"
---
# <a name="getdemultiplexedstub-function"></a>GetDemultiplexedStub (funzione)
Crea un sink di inoltro oggetti per consentire a un client di ricevere chiamate asincrone da Gestione Windows.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>Parametri

`pObject`  
in Puntatore all'implementazione in-process del client di [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).

`isLocal`  
in Flag che indica se l'evento è locale (`true`); in caso contrario,. `false`

`ppObject`  
out Sink di server d'avanzamento oggetto per consentire a un client di ricevere chiamate asincrone dalla gestione di Windows.

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito positivo, il valore `S_OK` restituito è (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero. Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo](geterrorinfo.md) .
    
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils. idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
