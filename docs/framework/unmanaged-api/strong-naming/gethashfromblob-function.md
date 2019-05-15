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
ms.openlocfilehash: 6ba049723710b378a90d17c67735a05e8a09d05d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636856"
---
# <a name="gethashfromblob-function"></a>Funzione GetHashFromBlob

Ottiene un hash dell'assembly all'indirizzo di memoria specificato usando l'algoritmo hash specificato.

Questa funzione è stata deprecata. Usare la [GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) metodo invece.

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
[in] Un puntatore all'indirizzo del blocco di memoria per eseguire l'hashing.

`cchBlob`\
[in] La lunghezza, espressa in byte, del blocco di memoria.

`piHashAlg`\
[in, out] Costante che specifica l'algoritmo hash. Usa lo zero per l'algoritmo predefinito.

`pbHash`\
[out] Il buffer di hash restituito.

`cchHash`\
[in] La dimensione massima richiesta del `pbHash`.

`pchHash`\
[out] Le dimensioni, in byte, del valore restituito `pbHash`.

## <a name="requirements"></a>Requisiti

**Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).

**Intestazione:** StrongName.h

**Libreria:** Inclusa come risorsa in Mscoree. dll

**Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]

## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
