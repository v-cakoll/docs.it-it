---
title: Get function (Unmanaged API Reference)
description: La funzione Get recupera il valore della proprietà specificato.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 67fcfb301eebfcf4ed4fdcaa5c9ddf85c47a6073
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174979"
---
# <a name="get-function"></a>Funzione Get

Recupera il valore della proprietà specificata, se esistente.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
HRESULT Get (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
);
```

## <a name="parameters"></a>Parametri

`vFunc`\
[in] Questo parametro non viene utilizzato.

`ptr`\
[in] Puntatore a [un'istanza di IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)

`wszName`\
[in] Nome della proprietà.

`lFlags`\
[in] Riservato. Questo parametro deve essere 0.

`pVal`\
[fuori] Se la funzione restituisce correttamente, contiene il valore della `wszName` proprietà. All'argomento `pval` vengono assegnati il tipo e il valore corretti per il qualificatore.

`pvtType`\
[fuori] Se la funzione restituisce correttamente, contiene una [costante di tipo CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) che indica il tipo di proprietà. Il suo valore `null`può anche essere .

`plFlavor`\
[fuori] Se la funzione restituisce correttamente, riceve informazioni sull'origine della proprietà. Il valore `null`può essere , o una delle seguenti costanti WBEM_FLAVOR_TYPE definite nel file di intestazione *WbemCli.h:*

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La proprietà è una proprietà di sistema standard. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Per una classe: la proprietà viene ereditata dalla classe padre. <br> Per un'istanza: la proprietà, sebbene ereditata dalla classe padre, non è stata modificata dall'istanza.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Per una classe: la proprietà appartiene alla classe derivata. <br> Per un'istanza: la proprietà viene modificata dall'istanza; ovvero è stato fornito un valore oppure è stato aggiunto o modificato un qualificatore. |

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | C'è stato un fallimento generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | La proprietà specificata non è stata trovata. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l’operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |

## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemClassObject::Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .

La `Get` funzione può anche restituire proprietà di sistema.

All'argomento `pVal` vengono assegnati il tipo e il valore corretti per il qualificatore e la funzione [COM VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)

## <a name="requirements"></a>Requisiti

 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils.idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
