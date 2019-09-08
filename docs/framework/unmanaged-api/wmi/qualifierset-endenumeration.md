---
title: Funzione QualifierSet_EndEnumeration (riferimenti alle API non gestite)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5a817174ec4c4e4407c19bb1d6d2d852d86dd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798326"
---
# <a name="qualifierset_endenumeration-function"></a>QualifierSet_EndEnumeration (funzione)
Termina l'enumerazione iniziata con una chiamata alla funzione [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) .  

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
in Questo parametro è inutilizzato.

`ptr`   
in Puntatore a un'istanza di [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) .

## <a name="return-value"></a>Valore restituito

Il valore seguente restituito da questa funzione è definito nel file di intestazione *WbemCli. h* oppure è possibile definirlo come costante nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IWbemQualifierSet:: EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) .

Questa chiamata è consigliata, ma non obbligatoria. Rilascia immediatamente le risorse associate all'enumerazione.

## <a name="requirements"></a>Requisiti  

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
**Intestazione:** WMINet_Utils. idl  
  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
