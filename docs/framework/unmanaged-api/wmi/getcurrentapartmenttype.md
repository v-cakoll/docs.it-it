---
title: Funzione GetCurrentApartmentType (riferimenti alle API non gestite)
description: "La funzione GetCurrentApartmentType recupera il tipo di apartment, in cui il chiamante è in esecuzione."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetCurrentApartmentType
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetCurrentApartmentType
helpviewer_keywords: GetCurrentApartmentType function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b250913b55ba59261a666760cc15466b6f9d096e
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2017
---
# <a name="getcurrentapartmenttype-function"></a>GetCurrentApartmentType (funzione)
Recupera il tipo di apartment, in cui il chiamante è in esecuzione.   
  
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
[in] Un puntatore a un [IComThreadingInfo](https://msdn.microsoft.com/library/windows/desktop/ms694502(v=vs.85).aspx) istanza.

`aptType`  
[out] Un puntatore a un [APTTYPE](https://msdn.microsoft.com/library/windows/desktop/ms693793(v=vs.85).aspx) valore di enumerazione che indica l'apartment del chiamante.

## <a name="return-value"></a>Valore restituito


|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `S_OK` | 0 | La funzione completata. |
| `E_FAIL` | 0x80000008 | Il chiamante non è in esecuzione in un apartment. |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IComThreadingInfo::GetCurrentApartmentType](https://msdn.microsoft.com/library/windows/desktop/ms683752(v=vs.85).aspx) metodo.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
