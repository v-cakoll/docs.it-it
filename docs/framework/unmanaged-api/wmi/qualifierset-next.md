---
title: QualifierSet_Next function (Unmanaged API Reference)
description: La funzione QualifierSet_Next recupera il qualificatore successivo in un'enumerazione.
ms.date: 11/06/2017
api_name:
- QualifierSet_Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_Next
helpviewer_keywords:
- QualifierSet_Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: d3702426bc409d601ccfc6b7a8e93e8d9729c64e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174875"
---
# <a name="qualifierset_next-function"></a>Funzione QualifierSet_Next
Recupera il qualificatore successivo in un'enumerazione avviata con una chiamata alla funzione [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT QualifierSet_Next (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr,
   [in] LONG                 lFlags,
   [out] BSTR*               pstrName,
   [out] VARIANT*            pVal,
   [out] LONG*               plFlavor
);
```  

## <a name="parameters"></a>Parametri

`vFunc`[in] Questo parametro non viene utilizzato.

`ptr`[in] Puntatore a [un'istanza di IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

`lFlags`[in] Riservati. Questo parametro deve essere 0.

`pstrName`[fuori] Nome del qualificatore. Se `null`, questo parametro viene ignorato; in `pstrName` caso contrario, `BSTR` non deve puntare a un valore valido o si verifica una perdita di memoria. Se non è null, la `BSTR` funzione alloca sempre un nuovo quando restituisce `WBEM_S_NO_ERROR`.

`pVal`[fuori] In caso di esito positivo, valore per il qualificatore. Se la funzione `VARIANT` ha esito negativo, l'oggetto indicato da `pVal` non viene modificato. Se questo `null`parametro è , il parametro viene ignorato.

`plFlavor`[fuori] Puntatore a un long che riceve il sapore del qualificatore. Se le informazioni sul sapore non `null`sono desiderate, questo parametro può essere .

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
|`WBEM_E_UNEXPECTED` | 0x8004101d | Il chiamante non ha chiamato [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md). |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per iniziare una nuova enumerazione. |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Non sono rimasti altri qualificatori nell'enumerazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemQualifierSet::Next.](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-next)

Chiamare la `QualifierSet_Next` funzione ripetutamente per enumerare tutti `WBEM_S_NO_MORE_DATA`i qualificatori fino a quando la funzione restituisce . Per terminare l'enumerazione in anticipo, chiamare la funzione [QualifierSet_EndEnumeration.](qualifierset-endenumeration.md)

L'ordine dei qualificatori restituiti durante l'enumerazione non è definito.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
