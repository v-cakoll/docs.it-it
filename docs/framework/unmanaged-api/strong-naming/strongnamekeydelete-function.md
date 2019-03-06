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
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57364515"
---
# <a name="strongnamekeydelete-function"></a>Funzione StrongNameKeyDelete

Elimina il contenitore di chiavi specificato.

Questa funzione è stata deprecata. Usare la [StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) metodo invece.

## <a name="syntax"></a>Sintassi

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a>Parametri

`wszKeyContainer`\
[in] Il nome del contenitore di chiavi da eliminare.

## <a name="return-value"></a>Valore restituito

`true` al termine dell'esecuzione; in caso contrario, `false`.

## <a name="remarks"></a>Note

Usare la [StrongNameKeyInstall](strongnamekeyinstall-function.md) (funzione) per importare una coppia di chiavi pubblica/privata in un contenitore.

Se il `StrongNameKeyDelete` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** StrongName.h

**Libreria:** Inclusa come risorsa in Mscoree. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [Metodo StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)