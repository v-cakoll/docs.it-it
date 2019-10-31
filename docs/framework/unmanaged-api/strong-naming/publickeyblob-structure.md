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
ms.openlocfilehash: 6c58a0726e0869178838999c6b000e0ad975f145
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140613"
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
  
## <a name="members"></a>Members  
  
|Member|Descrizione|  
|------------|-----------------|  
|`SigAlgId`|Identificatore per l'algoritmo di firma, di tipo `ALG_ID`, come definito in WinCrypt. h, della chiave pubblica.|  
|`HashAlgId`|Identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt. h) della chiave pubblica.|  
|`cbPublicKey`|Lunghezza in byte della chiave.|  
|`PublicKey`|Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.|  
  
## <a name="remarks"></a>Note  
 La struttura `PublicKeyBlob` viene utilizzata da [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)e altre funzioni con nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione StrongNameGetPublicKey](strongnamegetpublickey-function.md)
- [Funzione StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)
