---
title: Funzione GetHashFromBlob
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 59b4df08157ce14a58393e54b671e8f41b8998ed
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799226"
---
# <a name="gethashfromblob-function"></a>Funzione GetHashFromBlob

Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.

Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) .

## <a name="syntax"></a>Sintassi

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a>Parametri

`pbBlob`\
in Puntatore all'indirizzo del blocco di memoria di cui eseguire l'hashing.

`cchBlob`\
in Lunghezza, in byte, del blocco di memoria.

`piHashAlg`\
[in, out] Costante che specifica l'algoritmo hash. Usare zero per l'algoritmo predefinito.

`pbHash`\
out Buffer hash restituito.

`cchHash`\
in Dimensione massima richiesta di `pbHash`.

`pchHash`\
out Dimensione, in byte, dell'oggetto restituito `pbHash`.

## <a name="requirements"></a>Requisiti

**Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).

**Intestazione:** StrongName. h

**Libreria** Incluso come risorsa in MsCorEE. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
