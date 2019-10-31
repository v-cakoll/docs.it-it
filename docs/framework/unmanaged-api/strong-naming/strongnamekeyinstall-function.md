---
title: Funzione StrongNameKeyInstall
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125205"
---
# <a name="strongnamekeyinstall-function"></a>Funzione StrongNameKeyInstall

Importa una coppia di chiavi pubblica/privata in un contenitore.

Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) .

## <a name="syntax"></a>Sintassi

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a>Parametri

`wszKeyContainer`\
in Nome del contenitore di chiavi. `wszKeyContainer` deve essere una stringa non vuota.

`pbKeyBlob`\
in Coppia di chiavi binarie.

`cbKeyBlob`\
in Dimensione, in byte, del `pbKeyBlob`.

## <a name="return-value"></a>Valore restituito

`true` al completamento; in caso contrario, `false`.

## <a name="remarks"></a>Note

Usare la funzione [StrongNameKeyDelete](strongnamekeydelete-function.md) per eliminare il contenitore di chiavi.

Se la funzione `StrongNameKeyInstall` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** StrongName. h

**Libreria:** Incluso come risorsa in MsCorEE. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Metodo StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
