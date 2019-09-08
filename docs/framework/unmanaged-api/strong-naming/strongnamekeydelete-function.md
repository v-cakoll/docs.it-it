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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799028"
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

`true`al completamento; in caso `false`contrario,.

## <a name="remarks"></a>Note

Usare la funzione [StrongNameKeyInstall](strongnamekeyinstall-function.md) per importare una coppia di chiavi pubblica/privata in un contenitore.

Se la `StrongNameKeyDelete` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** StrongName. h

**Libreria** Incluso come risorsa in MsCorEE. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Metodo StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
