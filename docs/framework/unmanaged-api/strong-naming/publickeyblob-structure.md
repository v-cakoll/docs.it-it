---
title: Struttura PublicKeyBlob
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PublicKeyBlob
api_location: mscoree.dll
api_type: COM
f1_keywords: PublicKeyBlob
helpviewer_keywords: PublicKeyBlob structure [.NET Framework strong naming]
ms.assetid: b9240712-829c-4c8d-9a09-a6e7aa63f63a
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e273570c77b2855d942db580be95b040870a4c01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="publickeyblob-structure"></a>Struttura PublicKeyBlob
Rappresenta la chiave pubblica di una coppia di chiavi pubblica/privata, in formato binario.  
  
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
|`SigAlgId`|L'identificatore per l'algoritmo di firma (di tipo `ALG_ID`, come definito in WinCrypt) della chiave pubblica.|  
|`HashAlgId`|L'identificatore per l'algoritmo hash (di tipo `ALG_ID`, come definito in WinCrypt) della chiave pubblica.|  
|`cbPublicKey`|La lunghezza della chiave in byte.|  
|`PublicKey`|Una matrice di byte a lunghezza variabile che contiene il valore della chiave nel formato restituito da CryptoAPI.|  
  
## <a name="remarks"></a>Note  
 Il `PublicKeyBlob` struttura viene utilizzata dalla [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)e altre funzioni di nome sicuro per rappresentare la chiave pubblica di una coppia di chiavi pubblica/privata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [StrongNameGetPublicKey (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md)  
 [StrongNameSignatureGeneration (funzione)](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)  
 [Strutture di denominazione sicura](http://msdn.microsoft.com/en-us/4b041a2f-fd12-4b91-aacd-bc3b34a5124d)
