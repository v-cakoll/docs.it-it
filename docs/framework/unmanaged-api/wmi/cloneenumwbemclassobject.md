---
title: Funzione CloneEnumWbemClassObject (riferimenti alle API non gestite)
description: La funzione CloneEnumWbemClassObject crea una copia logica di un enumeratore.
ms.date: 11/06/2017
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
ms.openlocfilehash: 1605314f94fd82d2a2cd7be105dde9e273f607bc
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798693"
---
# <a name="cloneenumwbemclassobject-function"></a>Funzione CloneEnumWbemClassObject
Crea una copia logica di un enumeratore mantenendone la posizione corrente in un'enumerazione.

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a>Sintassi

```cpp
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

`ppEnum`\
out Riceve un puntatore a un nuovo [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
in Livello di autorizzazione.

`impLevel`\
in Livello di rappresentazione.

`pCurrentEnumWbemClassObject`\
out Puntatore all'istanza di [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) da clonare.

`strUser`\
in Nome utente. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .

`strPassword`\
in Password. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .

`strAuthority`[in] nome di dominio dell'utente. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi](connectserverwmi.md) .

## <a name="return-value"></a>Valore restituito

I valori seguenti restituiti da questa funzione sono definiti nel file di intestazione *WbemCli. h* oppure è possibile definirli come costanti nel codice:

|Costante  |Value  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | Si è verificato un errore generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | La memoria disponibile non è sufficiente per completare l'operazione. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione è stata completata.  |

## <a name="remarks"></a>Note

Questa funzione esegue il wrapping di una chiamata al metodo [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .

Questo metodo esegue solo una copia "Best Effort". A causa della natura dinamica di molti oggetti CIM, è possibile che il nuovo enumeratore non enumera lo stesso set di oggetti dell'enumeratore di origine.

Se la chiamata di funzione ha esito negativo, è possibile ottenere ulteriori informazioni sull'errore chiamando la funzione [GetErrorInfo](geterrorinfo.md) .

## <a name="example"></a>Esempio

Per un esempio, vedere il metodo [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .

## <a name="requirements"></a>Requisiti
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils. idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
