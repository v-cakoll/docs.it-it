---
title: Funzione Next (riferimenti alle API non gestite)
description: La funzione Next recupera la proprietà Next in un'enumerazione.
ms.date: 11/06/2017
api_name:
- Next
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Next
helpviewer_keywords:
- Next function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 587e085f6fe9f6c19d3605c673cd3bd6f68162f1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127371"
---
# <a name="next-function"></a>Next (funzione)
Recupera la proprietà successiva in un'enumerazione che inizia con una chiamata a [BeginEnumeration](beginenumeration.md).

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Next (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lFlags,
   [out] BSTR*            pstrName,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`lFlags`\
[in] Riservato. Questo parametro deve essere 0.

`pstrName`\
out Nuovo `BSTR` contenente il nome della proprietà. È possibile impostare questo parametro su `null` se il nome non è obbligatorio.

`pVal`\
out `VARIANT` riempita con il valore della proprietà. È possibile impostare questo parametro su `null` se il valore non è obbligatorio. Se la funzione restituisce un codice di errore, il `VARIANT` passato a `pVal` viene lasciato invariato.

`pvtType`\
out Puntatore a una variabile di `CIMTYPE` (`LONG` in cui viene inserito il tipo della proprietà). Il valore di questa proprietà può essere un `VT_NULL_VARIANT`, nel qual caso è necessario determinare il tipo effettivo della proprietà. Questo parametro può anche essere `null`.

`plFlavor`\
[out] `null`o un valore che riceve informazioni sull'origine della proprietà. Per i valori possibili, vedere la sezione [osservazioni].

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_UNEXPECTED` | 0x8004101d | Non è stata chiamata la funzione [`BeginEnumeration`](beginenumeration.md) . |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | La memoria disponibile non è sufficiente per iniziare una nuova enumerazione. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | La chiamata di procedura remota tra il processo corrente e la gestione di Windows non è riuscita. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
| `WBEM_S_NO_MORE_DATA` | 0x40005 | Non sono presenti altre proprietà nell'enumerazione. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: Next](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-next) .

Questo metodo restituisce anche le proprietà di sistema.

Se il tipo sottostante della proprietà è un percorso di oggetto, una data o un'ora o un altro tipo speciale, il tipo restituito non contiene informazioni sufficienti. Il chiamante deve esaminare la `CIMTYPE` per la proprietà specificata per determinare se la proprietà è un riferimento a un oggetto, una data o un'ora o un altro tipo speciale.

Se `plFlavor` non è `null`, il valore `LONG` riceve informazioni sull'origine della proprietà, come indicato di seguito:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La proprietà è una proprietà di sistema standard. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Per una classe: la proprietà viene ereditata dalla classe padre. <br> Per un'istanza: la proprietà, mentre ereditata dalla classe padre, non è stata modificata dall'istanza di.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Per una classe: la proprietà appartiene alla classe derivata. <br> Per un'istanza: la proprietà viene modificata dall'istanza di. ovvero è stato specificato un valore oppure è stato aggiunto o modificato un qualificatore. |

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
