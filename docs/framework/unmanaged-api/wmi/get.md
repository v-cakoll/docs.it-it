---
title: Funzione Get (riferimenti alle API non gestite)
description: La funzione Get recupera il valore della proprietà specificata.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 265d3edbd3175eebcf6fd35be24f5b66144c960f
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037946"
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
in Questo parametro è inutilizzato.

`ptr`\
in Puntatore a un'istanza di [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .

`wszName`\
in Nome della proprietà.

`lFlags`\
[in] Riservato. Questo parametro deve essere 0.

`pVal`\
out Se la funzione restituisce correttamente, contiene il valore della `wszName` proprietà. All' `pval` argomento vengono assegnati il tipo e il valore corretti per il qualificatore.

`pvtType`\
out Se la funzione restituisce correttamente, contiene una [costante di tipo CIM](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) che indica il tipo di proprietà. Il valore può essere `null`anche. 

`plFlavor`\
out Se la funzione restituisce correttamente, riceve informazioni sull'origine della proprietà. Il valore può essere `null`o una delle seguenti costanti WBEM_FLAVOR_TYPE definite nel file di intestazione *WbemCli. h* : 

|Costante  |Value  |DESCRIZIONE  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | 0x40 | La proprietà è una proprietà di sistema standard. |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | 0x20 | Per una classe: La proprietà viene ereditata dalla classe padre. <br> Per un'istanza: La proprietà, mentre ereditata dalla classe padre, non è stata modificata dall'istanza di.  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | 0 | Per una classe: La proprietà appartiene alla classe derivata. <br> Per un'istanza: La proprietà viene modificata dall'istanza di. ovvero è stato specificato un valore oppure è stato aggiunto o modificato un qualificatore. |

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | Uno o più parametri non sono validi. |
|`WBEM_E_NOT_FOUND` | 0x80041002 | Impossibile trovare la proprietà specificata. |
|`WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemClassObject:: Get](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-get) .

La `Get` funzione può inoltre restituire proprietà di sistema.

All' `pVal` argomento vengono assegnati il tipo e il valore corretti per il qualificatore e la funzione com [VariantInit](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantinit)

## <a name="requirements"></a>Requisiti

 **Piattaforme** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils. idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
