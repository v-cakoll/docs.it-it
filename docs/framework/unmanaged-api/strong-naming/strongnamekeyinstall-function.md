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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799002"
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
in Nome del contenitore di chiavi. `wszKeyContainer`deve essere una stringa non vuota.

`pbKeyBlob`\
in Coppia di chiavi binarie.

`cbKeyBlob`\
in Dimensione, in byte, di `pbKeyBlob`.

## <a name="return-value"></a>Valore restituito

`true`al completamento; in caso `false`contrario,.

## <a name="remarks"></a>Note

Usare la funzione [StrongNameKeyDelete](strongnamekeydelete-function.md) per eliminare il contenitore di chiavi.

Se la `StrongNameKeyInstall` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** StrongName. h

**Libreria** Incluso come risorsa in MsCorEE. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Metodo StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
