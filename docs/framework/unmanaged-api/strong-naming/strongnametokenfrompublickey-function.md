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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fbfd3ae32f4d3033894fdaf6b1bcc880c324e928
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219798"
---
# <a name="strongnametokenfrompublickey-function"></a>Funzione StrongNameTokenFromPublicKey
Ottiene un token che rappresenta una chiave pubblica. Un token con nome sicuro è il formato abbreviato di una chiave pubblica.  
  
 Questa funzione è stata deprecata. Usare la [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbPublicKeyBlob`  
 [in] Una struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi usata per generare la firma con nome sicuro.  
  
 `cbPublicKeyBlob`  
 [in] Le dimensioni, in byte, di `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 [out] Il token di nome sicuro corrispondente alla chiave passato `pbPublicKeyBlob`. Common language runtime alloca la memoria in cui restituire il token. Il chiamante deve liberare la memoria usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).  
  
 `pcbStrongNameToken`  
 [out] Le dimensioni, in byte, del token restituito nome sicuro.  
  
## <a name="return-value"></a>Valore restituito  
 `true` al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Un token con nome sicuro è il formato abbreviato di una chiave pubblica usata per risparmiare spazio quando si archiviano le informazioni sulla chiave nei metadati. In particolare, i token di nome sicuro vengono usati nei riferimenti ad assembly per fare riferimento all'assembly dipendenti.  
  
 Se il `StrongNameTokenFromPublicKey` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Metodo StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Struttura PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
