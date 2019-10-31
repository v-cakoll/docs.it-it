---
title: Funzione StrongNameKeyDelete
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141590"
---
# <a name="strongnamekeydelete-function"></a>Funzione StrongNameKeyDelete

Elimina il contenitore di chiavi specificato.

Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) .

## <a name="syntax"></a>Sintassi

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Parametri

`wszKeyContainer`\
in Nome del contenitore di chiavi da eliminare.

## <a name="return-value"></a>Valore restituito

`true` al completamento; in caso contrario, `false`.

## <a name="remarks"></a>Note

Usare la funzione [StrongNameKeyInstall](strongnamekeyinstall-function.md) per importare una coppia di chiavi pubblica/privata in un contenitore.

Se la funzione `StrongNameKeyDelete` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** StrongName. h

**Libreria:** Incluso come risorsa in MsCorEE. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Metodo StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
