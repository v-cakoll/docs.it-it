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
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140719"
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
in Dimensioni massime richieste di `pbHash`.

`pchHash`\
out Dimensione, in byte, dell'oggetto restituito `pbHash`.

## <a name="requirements"></a>Requisiti

**Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).

**Intestazione:** StrongName. h

**Libreria:** Incluso come risorsa in MsCorEE. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
