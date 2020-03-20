---
title: Funzione CloneEnumWbemClassObject (riferimenti all'API non gestita)
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
ms.openlocfilehash: f2a3a7e848108e50c04f0ec70cf42586755a0a88
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175018"
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
[fuori] Riceve un puntatore a un nuovo [oggetto IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).

`authLevel`\
[in] Livello di autorizzazione.

`impLevel`\
[in] Livello di rappresentazione.

`pCurrentEnumWbemClassObject`\
[fuori] Puntatore all'istanza di [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) da clonare.

`strUser`\
[in] Nome utente. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)

`strPassword`\
[in] La password. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)

`strAuthority`\
[in] Nome di dominio dell'utente. Per ulteriori informazioni, vedere la funzione [ConnectServerWmi.](connectserverwmi.md)

## <a name="return-value"></a>Valore restituito

I seguenti valori restituiti da questa funzione sono definiti nel file di intestazione WbemCli.h oppure è possibile definirli come costanti nel codice:The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:

|Costante  |valore  |Descrizione  |
|---------|---------|---------|
| `WBEM_E_FAILED` | 0x80041001 | C'è stato un fallimento generale. |
| `WBEM_E_INVALID_PARAMETER` | 0x80041008 | Un parametro non è valido. |
| `WBEM_E_OUT_OF_MEMORY` | 0x80041006 | Memoria insufficiente per completare l'operazione. |
| `WBEM_E_TRANSPORT_FAILURE` | 0x80041015 | Il collegamento RPC (Remote Procedure Call) tra il processo corrente e WMI non è riuscito. |
| `WBEM_S_NO_ERROR` | 0 | La chiamata di funzione ha avuto esito positivo.  |

## <a name="remarks"></a>Osservazioni

Questa funzione esegue il wrapping di una chiamata al metodo [IEnumWbemClassObject::Clone.](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone)

Questo metodo fa solo una copia "migliore sforzo". A causa della natura dinamica di molti oggetti CIM, è possibile che il nuovo enumeratore non enumeri lo stesso set di oggetti dell'enumeratore di origine.

Se la chiamata di funzione ha esito negativo, è possibile ottenere informazioni aggiuntive sull'errore chiamando la funzione [GetErrorInfo.If](geterrorinfo.md) the function call fails, you can obtain additional error information by calling the GetErrorInfo function.

## <a name="example"></a>Esempio

Per un esempio, vedere il [metodo IEnumWbemClassObject::Clone.For an example, see the IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.

## <a name="requirements"></a>Requisiti
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

 **Intestazione:** WMINet_Utils.idl

 **Versioni di .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]

## <a name="see-also"></a>Vedere anche

- [WMI e contatori delle prestazioni (riferimenti alle API non gestite)](index.md)
