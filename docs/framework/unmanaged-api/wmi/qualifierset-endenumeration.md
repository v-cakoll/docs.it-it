---
title: QualifierSet_EndEnumeration function (Unmanaged API Reference)
description: La funzione QualifierSet_EndEnumeration termina un'enumerazione.
ms.date: 11/06/2017
api_name:
- QualifierSet_EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- QualifierSet_EndEnumeration
helpviewer_keywords:
- QualifierSet_EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: c606580ff2e02c5659c14b134b1a17a65651952b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176747"
---
# <a name="qualifierset_endenumeration-function"></a>Funzione QualifierSet_EndEnumeration
Termina l'enumerazione iniziata con una chiamata alla funzione [QualifierSet_BeginEnumeration.](qualifierset-beginenumeration.md)  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc,
   [in] IWbemQualifierSet*   ptr
);
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro non viene utilizzato.

`ptr`[in] Puntatore a [un'istanza di IWbemQualifierSet.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset)

## <a name="return-value"></a>Valore restituito

Il seguente valore restituito da questa funzione è definito nel file di intestazione WbemCli.h oppure è possibile definirlo come costante nel codice:The following value returned by this function is defined in the *WbemCli.h* header file, or you can define it as a constant in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |
  
## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al [metodo IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .

Questa chiamata è consigliata, ma non obbligatoria. Rilascia immediatamente le risorse associate all'enumerazione.

## <a name="requirements"></a>Requisiti  

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
**Intestazione:** WMINet_Utils.idl  
  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
