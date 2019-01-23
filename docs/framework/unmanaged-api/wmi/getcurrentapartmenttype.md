---
title: Funzione GetCurrentApartmentType (riferimenti alle API non gestite)
description: La funzione GetCurrentApartmentType recupera il tipo di apartment in cui è in esecuzione al chiamante.
ms.date: 11/06/2017
api_name:
- GetCurrentApartmentType
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetCurrentApartmentType
helpviewer_keywords:
- GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a999dc1850a41612f8896ff9a7ed96cd8c3a2fe
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54509135"
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType (funzione)
Recupera il tipo di apartment in cui il chiamante è in esecuzione.   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetCurrentApartmentType (
   [in] int                   vFunc, 
   [in] IComThreadingInfo*    ptr, 
   [out] APTTYPE*             aptType
); 
```  

## <a name="parameters"></a>Parametri

`vFunc`  
[in] Questo parametro è inutilizzato.

`ptr`  
[in] Un puntatore a un [IComThreadingInfo](/windows/desktop/api/objidlbase/nn-objidlbase-icomthreadinginfo) istanza.

`aptType`  
[out] Un puntatore a un [APTTYPE](/windows/desktop/api/objidlbase/ne-objidlbase-_apttype) valore di enumerazione che indica l'apartment del chiamante.

## <a name="return-value"></a>Valore restituito


|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `S_OK` | 0 | La funzione è stata completata correttamente. |
| `E_FAIL` | 0x80000008 | Il chiamante non è in esecuzione in un apartment. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata per il [IComThreadingInfo::GetCurrentApartmentType](/windows/desktop/api/objidlbase/nf-objidlbase-icomthreadinginfo-getcurrentapartmenttype) (metodo).

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche
- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
