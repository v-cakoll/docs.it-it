---
title: Metodo ICLRStrongName::StrongNameGetPublicKey
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9a639644405ce215a373dadf248e9a0e1a5558ba
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>Metodo ICLRStrongName::StrongNameGetPublicKey
Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. La coppia di chiavi può essere fornita come un nome di contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come una raccolta di byte non elaborata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szKeyContainer`  
 [in] Il nome del contenitore di chiavi contenente la coppia di chiavi pubblica/privata. Se `pbKeyBlob` è null, `szKeyContainer` deve specificare un contenitore valido all'interno del CSP. In questo caso, il [ICLRStrongName:: StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) metodo estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().  
  
 Le chiavi devono essere Rivest-Shamir-Adleman (RSA a 1024 bit) le chiavi di firma. Nessun altro tipo di chiavi è supportato in questo momento.  
  
 `pbKeyBlob`  
 [in] Un puntatore per la coppia di chiavi pubblica/privata. Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione). Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `szKeyContainer` si presuppone che la coppia di chiavi.  
  
 `cbKeyBlob`  
 [in] Le dimensioni, in byte, di `pbKeyBlob`.  
  
 `ppbPublicKeyBlob`  
 [out] Chiave pubblica restituita BLOB. Il `ppbPublicKeyBlob` parametro è allocata da common language runtime e restituito al chiamante. Il chiamante deve liberare la memoria utilizzando il [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo.  
  
 `pcbPublicKeyBlob`  
 [out] Le dimensioni della chiave pubblica restituita BLOB.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 La chiave pubblica è contenuta un [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) struttura.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)  
 [Struttura PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
