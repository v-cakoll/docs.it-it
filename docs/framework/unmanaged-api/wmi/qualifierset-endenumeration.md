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
ms.openlocfilehash: a9d3f8966f6333487631a0e155c7be49075a6992
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54734675"
---
# <a name="qualifiersetendenumeration-function"></a>QualifierSet_EndEnumeration (funzione)
Termina l'enumerazione iniziato con una chiamata per il [QualifierSet_BeginEnumeration](qualifierset-beginenumeration.md) (funzione).  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT QualifierSet_EndEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`   
[in] Un puntatore a un [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) istanza.

## <a name="return-value"></a>Valore restituito

Il valore seguente restituito da questa funzione è definito nel *WbemCli.h* file di intestazione, oppure è possibile definirlo come costante nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemQualifierSet::EndEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemqualifierset-endenumeration) (metodo).

Questa chiamata è consigliata, ma non obbligatorio. Rilascia immediatamente le risorse associate all'enumerazione.

## <a name="requirements"></a>Requisiti  

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
**Intestazione:** WMINet_Utils.idl  
  
**Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche
- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
