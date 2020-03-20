---
title: GetDemultiplexedStub function (Unmanaged API Reference)
description: La funzione GetDemultiplexedStub crea un sink di inoltro oggetto per assistere un client nella ricezione di chiamate asincrone da Gestione Windows.The GetDemultiplexedStub function creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.
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
ms.openlocfilehash: d15fed261db2ca2cda6dbf824dc9cb0d5c56eed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174966"
---
# <a name="getdemultiplexedstub-function"></a>Funzione GetDemultiplexedStub
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
[in] Puntatore all'implementazione in-process del client di [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).

`isLocal`  
[in] Flag che indica se l'evento`true`è locale ( ); in `false`caso contrario, .

`ppObject`  
[fuori] Un sink del server di inoltro oggetto per assistere un client nella ricezione di chiamate asincrone da Gestione Windows.

## <a name="return-value"></a>Valore restituito

Se la funzione ha esito `S_OK` positivo, il valore restituito è (0).

Se la funzione ha esito negativo, il valore restituito è un codice di errore diverso da zero. Per ottenere informazioni estese sull'errore, chiamare la funzione [GetErrorInfo.To](geterrorinfo.md) get extended error information, call the GetErrorInfo function.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
