---
title: Funzione StrongNameTokenFromPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- StrongNameTokenFromPublicKey
helpviewer_keywords:
- StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type:
- apiref
ms.openlocfilehash: b95c96efeb666f25d04118aa8cb9b0da3a2e7924
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104155"
---
# <a name="strongnametokenfrompublickey-function"></a>Funzione StrongNameTokenFromPublicKey
Ottiene un token che rappresenta una chiave pubblica. Un token di nome sicuro è il formato abbreviato di una chiave pubblica.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbPublicKeyBlob`  
 in Struttura di tipo [PublicKeyBlob](publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.  
  
 `cbPublicKeyBlob`  
 in Dimensione, in byte, del `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 out Token del nome sicuro corrispondente alla chiave passata `pbPublicKeyBlob`. Il Common Language Runtime alloca la memoria in cui restituire il token. Il chiamante deve liberare questa memoria tramite la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) .  
  
 `pcbStrongNameToken`  
 out Dimensione, in byte, del token del nome sicuro restituito.  
  
## <a name="return-value"></a>Valore restituito  
 `true` al completamento; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Un token di nome sicuro è il formato abbreviato di una chiave pubblica usata per risparmiare spazio durante l'archiviazione delle informazioni chiave nei metadati. In particolare, i token con nome sicuro vengono utilizzati nei riferimenti ad assembly per fare riferimento all'assembly dipendente.  
  
 Se la funzione `StrongNameTokenFromPublicKey` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria:** Incluso come risorsa in mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Metodo StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Struttura PublicKeyBlob](publickeyblob-structure.md)
