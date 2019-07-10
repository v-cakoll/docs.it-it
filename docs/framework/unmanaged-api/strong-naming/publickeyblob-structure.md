---
title: Struttura PublicKeyBlob
ms.date: 03/30/2017
api_name:
- PublicKeyBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- PublicKeyBlob
helpviewer_keywords:
- PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75ba3fd634b108c996e848f48000ffcd0600b00c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774589"
---
# <a name="publickeyblob-structure"></a>Struttura PublicKeyBlob
Rappresenta, in formato binario, la chiave pubblica di una coppia di chiavi pubblica/privata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>Membri  
  
|Member|Descrizione|  
|------------|-----------------|  
|`SigAlgId`|L'identificatore per l'algoritmo di firma (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.|  
|`HashAlgId`|L'identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.|  
|`cbPublicKey`|La lunghezza della chiave in byte.|  
|`PublicKey`|Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.|  
  
## <a name="remarks"></a>Note  
 Il `PublicKeyBlob` struttura viene utilizzata dai [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)e altre funzioni di nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)
- [Funzione StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)
