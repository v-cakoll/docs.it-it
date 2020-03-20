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
ms.openlocfilehash: 20be3114908ef78966eead05ae8ba6333a491404
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175057"
---
# <a name="strongnametokenfrompublickey-function"></a>Funzione StrongNameTokenFromPublicKey
Ottiene un token che rappresenta una chiave pubblica. Un token con nome sicuro è la forma abbreviata di una chiave pubblica.  
  
 Questa funzione è deprecata. Utilizzare invece il metodo [ICLRStrongName::StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md) .  
  
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
 [in] Struttura di tipo [PublicKeyBlob](publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.  
  
 `cbPublicKeyBlob`  
 [in] Dimensione, in byte, `pbPublicKeyBlob`di .  
  
 `ppbStrongNameToken`  
 [fuori] Token con nome sicuro corrispondente `pbPublicKeyBlob`alla chiave passata in . Common Language Runtime alloca la memoria in cui restituire il token. Il chiamante deve liberare questa memoria utilizzando la funzione [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)  
  
 `pcbStrongNameToken`  
 [fuori] Dimensione, in byte, del token del nome sicuro restituito.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al termine del successo; in `false`caso contrario, .  
  
## <a name="remarks"></a>Osservazioni  
 Un token con nome sicuro è la forma abbreviata di una chiave pubblica utilizzata per risparmiare spazio durante l'archiviazione delle informazioni sulla chiave nei metadati. In particolare, i token con nome sicuro vengono utilizzati nei riferimenti all'assembly per fare riferimento all'assembly dipendente.  
  
 Se `StrongNameTokenFromPublicKey` la funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** NomeForte.h  
  
 **Biblioteca:** Incluso come risorsa in mscoree.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Metodo StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Struttura PublicKeyBlob](publickeyblob-structure.md)
