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
ms.openlocfilehash: e66196e2bd2cb326ca3f5badc67bcf8d81e5fc3c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799170"
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
  
|Member|DESCRIZIONE|  
|------------|-----------------|  
|`SigAlgId`|Identificatore per l'algoritmo di firma, di tipo `ALG_ID`, come definito in WinCrypt. h, della chiave pubblica.|  
|`HashAlgId`|Identificatore dell'algoritmo hash, di tipo `ALG_ID`, come definito in WinCrypt. h, della chiave pubblica.|  
|`cbPublicKey`|Lunghezza in byte della chiave.|  
|`PublicKey`|Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.|  
  
## <a name="remarks"></a>Note  
 La `PublicKeyBlob` struttura viene utilizzata da [StrongNameGetPublicKey](strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)e altre funzioni con nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Funzione StrongNameGetPublicKey](strongnamegetpublickey-function.md)
- [Funzione StrongNameSignatureGeneration](strongnamesignaturegeneration-function.md)
