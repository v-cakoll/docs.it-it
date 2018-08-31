---
title: Funzione GetMethodQualifierSet (riferimenti alle API non gestite)
description: La funzione GetMethodQualifierSet recupera set di qualificatore del metodo.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a363591f5db7a2dbcba1147df35d8c023c9b0707
ms.sourcegitcommit: a368166a51e5204c0224fbf5e46476e3ed122817
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/31/2018
ms.locfileid: "43332112"
---
# <a name="getmethodqualifierset-function"></a>GetMethodQualifierSet (funzione)
Recupera il qualificatore impostato per un particolare metodo.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) istanza.

`wszMethod`  
[in] Il nome del metodo. `wszMethod` deve puntare a un valore valido `LPCWSTR`. 

`ppQualSet`  
[out] Riceve il puntatore a interfaccia che consente l'accesso per i qualificatori del metodo. Il parametro `ppQualSet` non può essere `null`. Se si verifica un errore, non viene restituito un nuovo oggetto e il puntatore viene impostato in modo che punti a `null`. 

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirle come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | 0x80041002 | Il metodo specificato non esiste. |
|`WBEM_E_INVALID_PARAMETER` | 0x80041008 | È un parametro `null`. |
|`WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è riuscita.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) (metodo). 

Una chiamata a questa funzione è supportata solo se l'oggetto corrente è una definizione di classe CIM. Manipolazione di metodo non è disponibile per [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) ponters che puntano a istanze CIM.

Poiché ogni metodo può avere un proprio qualificatori, il [puntatore IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) consente al chiamante di aggiungere, modificare o eliminare questi qualificatori.

## <a name="requirements"></a>Requisiti  
**Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
