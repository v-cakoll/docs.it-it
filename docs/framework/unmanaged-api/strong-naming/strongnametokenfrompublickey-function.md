---
title: Funzione StrongNameTokenFromPublicKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: COM
f1_keywords: StrongNameTokenFromPublicKey
helpviewer_keywords: StrongNameTokenFromPublicKey function [.NET Framework strong naming]
ms.assetid: 997e9e57-abb2-4217-bf20-1df621a75add
topic_type: apiref
caps.latest.revision: "19"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0cb649f43bfea2e11c986aa3fff5a702e2b58c25
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnametokenfrompublickey-function"></a>Funzione StrongNameTokenFromPublicKey
Ottiene un token che rappresenta una chiave pubblica. Un token con nome sicuro è la forma abbreviata di una chiave pubblica.  
  
 Questa funzione è stata deprecata. Utilizzare il [:: StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEANStrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbPublicKeyBlob`  
 [in] Una struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi usata per generare la firma nome sicuro.  
  
 `cbPublicKeyBlob`  
 [in] Le dimensioni, in byte, di `pbPublicKeyBlob`.  
  
 `ppbStrongNameToken`  
 [out] Il token con nome sicuro corrispondente alla chiave passata `pbPublicKeyBlob`. Common language runtime alloca la memoria nel quale restituire il token. Il chiamante deve liberare la memoria utilizzando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).  
  
 `pcbStrongNameToken`  
 [out] Le dimensioni in byte, del token restituito con nome sicuro.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Un token con nome sicuro è la forma abbreviata di una chiave pubblica utilizzata per risparmiare spazio quando si archiviano le informazioni sulla chiave nei metadati. In particolare, vengono utilizzati i token con nome sicuro nei riferimenti ad assembly per fare riferimento all'assembly dipendenti.  
  
 Se il `StrongNameTokenFromPublicKey` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in mscoree.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [Metodo StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)  
 [Struttura PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
