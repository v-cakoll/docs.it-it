---
title: Funzione CloneEnumWbemClassObject (riferimenti alle API non gestite)
description: La funzione CloneEnumWbemClassObject effettua una copia logica di un enumeratore.
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22bcf2731ff682bf538858fc66a7a94be7f5d7df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="cloneenumwbemclassobject-function"></a>CloneEnumWbemClassObject (funzione)
Crea una copia logica di un enumeratore, mantenendo la posizione corrente nell'enumerazione.  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a>Parametri

`ppEnum`  
[out] Riceve un puntatore a un nuovo [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx).

`authLevel`  
[in] Il livello di autorizzazione.

`impLevel`[in] Il livello di rappresentazione.

`pCurrentEnumWbemClassObject`  
[out] Un puntatore al [IEnumWbemClassObject](https://msdn.microsoft.com/library/aa390857(v=vs.85).aspx) istanza da duplicare.

`strUser`   
[in] Il nome utente. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

`strPassword`   
[in] La password. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

`strAuthority`   
[in] Il nome di dominio dell'utente. Vedere il [ConnectServerWmi](connectserverwmi.md) funzione per ulteriori informazioni.

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel *WbemCli.h* file di intestazione, oppure è possibile definirli come costanti nel codice:

|Costante  |Valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente è disponibile completare l'operazione. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento remote procedure call (RPC) tra il processo corrente e WMI non riuscita. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |
  
## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metodo.

Questo metodo copia solo "best effort". A causa della natura dinamica di molti oggetti CIM, è possibile che il nuovo enumeratore non enumera lo stesso set di oggetti l'enumeratore di origine.  

Se la chiamata di funzione non riesce, è possibile ottenere informazioni aggiuntive sull'errore chiamando il [GetErrorInfo](geterrorinfo.md) (funzione).

## <a name="example"></a>Esempio

Per un esempio, vedere il [IEnumWbemClassObject::Clone](https://msdn.microsoft.com/library/aa390859(v=vs.85).aspx) metodo.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** WMINet_Utils.idl  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vedere anche  
[WMI e i contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
