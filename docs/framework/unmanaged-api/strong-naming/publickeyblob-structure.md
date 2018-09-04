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
ms.openlocfilehash: fd7a4b19613ea771a055af7dd91ec368859ee191
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43529134"
---
# <a name="publickeyblob-structure"></a>Struttura PublicKeyBlob
Rappresenta, in formato binario, la chiave pubblica di una coppia di chiavi pubblica/privata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct {  
    unsigned int SigAlgId;  
    unsigned int HashAlgId;  
    ULONG cbPublicKey;  
    BYTE PublicKey[1]  
} PublicKeyBlob;   
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`SigAlgId`|L'identificatore per l'algoritmo di firma (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.|  
|`HashAlgId`|L'identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt. H) della chiave pubblica.|  
|`cbPublicKey`|La lunghezza della chiave in byte.|  
|`PublicKey`|Matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.|  
  
## <a name="remarks"></a>Note  
 Il `PublicKeyBlob` struttura viene utilizzata dai [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)e altre funzioni di nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Funzione StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [Funzione StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [Strutture di denominazione sicura](https://msdn.microsoft.com/library/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
