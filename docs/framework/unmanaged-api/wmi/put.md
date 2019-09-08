---
title: Funzione Put (riferimenti alle API non gestite)
description: La funzione put assegna un nuovo valore a una proprietà denominata.
ms.date: 11/06/2017
api_name:
- Put
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Put
helpviewer_keywords:
- Put function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5aa629c2d07fb25db035cd80aba3c74413070e6e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798394"
---
# <a name="put-function"></a>Funzione put

Imposta una proprietà denominata su un nuovo valore.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Put (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [in] VARIANT*          pVal,
   [in] CIMTYPE           vtType
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
in Nome della proprietà. Questo parametro non può `null`essere.

`lFlags`\
[in] Riservato. Questo parametro deve essere 0.

`pVal`\
in Puntatore a un oggetto valido `VARIANT` che diventa il nuovo valore della proprietà. Se `pVal` `VARIANT` è `null` o punta a un oggetto di `VT_NULL`tipo, la proprietà viene impostata `null`su.

`vtType`\
in Tipo di `VARIANT` `pVal`a cui punta. Per ulteriori informazioni, vedere la sezione [osservazioni](#remarks) .

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi. |
|`WBEM_E_INVALID_PROPERTY_TYPE` | 0x8004102a | Il tipo di proprietà non è riconosciuto. Questo valore viene restituito quando si creano istanze della classe se la classe esiste già. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_TYPE_MISMATCH` | 0x80041005 | Per le istanze: Indica che `pVal` punta a un `VARIANT` oggetto di un tipo non corretto per la proprietà. <br/> Per le definizioni di classe: La proprietà esiste già nella classe padre e il nuovo tipo COM è diverso dal tipo COM precedente. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata. |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .

Questa funzione sovrascrive sempre il valore della proprietà corrente con uno nuovo. Se [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a una definizione di classe, `Put` crea o aggiorna il valore della proprietà. Quando [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punta a un'istanza CIM, `Put` aggiorna solo il valore della proprietà. `Put` non è possibile creare un valore della proprietà.

La `__CLASS` proprietà di sistema è scrivibile solo durante la creazione della classe, quando potrebbe non essere lasciata vuota. Tutte le altre proprietà di sistema sono di sola lettura.

Un utente non può creare proprietà con nomi che iniziano o terminano con un carattere di sottolineatura ("_"). Questa operazione è riservata per le classi e le proprietà di sistema.

Se la proprietà impostata dalla `Put` funzione esiste nella classe padre, il valore predefinito della proprietà viene modificato a meno che il tipo di proprietà non corrisponda al tipo di classe padre. Se la proprietà non esiste e non è un tipo non corrispondente, viene creata la proprietà.

Usare il `vtType` parametro solo quando si creano nuove proprietà in una definizione di classe `pVal` CIM `null` e è o fa `VARIANT` riferimento a `VT_NULL`un oggetto di tipo. In questo caso, il `vType` parametro specifica il tipo CIM della proprietà. In tutti gli altri casi `vtType` , deve essere 0. `vtType`deve anche essere 0 se l'oggetto sottostante è un'istanza (anche se `Val` è `null`) perché il tipo della proprietà è fisso e non può essere modificato.

## <a name="example"></a>Esempio

Per un esempio, vedere il metodo [IWbemClassObject::P UT](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-put) .

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** WMINet_Utils. idl

**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
