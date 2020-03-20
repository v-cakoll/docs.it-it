---
title: Metodo ICLRStrongName::StrongNameGetPublicKey
ms.date: 03/30/2017
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
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181929"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a>Metodo ICLRStrongName::StrongNameGetPublicKey
Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. La coppia di chiavi può essere fornita come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta non elaborata di byte.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szKeyContainer`  
 [in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata. Se `pbKeyBlob` è `szKeyContainer` null, è necessario specificare un contenitore valido all'interno del CSP. In questo caso, il metodo [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nell'oggetto binario di grandi dimensioni chiave (BLOB).  
  
 Le chiavi devono essere chiavi di firma RSA (Rivest-Shamir-Adleman) a 1024 bit. Al momento non sono supportati altri tipi di chiavi.  
  
 `pbKeyBlob`  
 [in] Puntatore alla coppia di chiavi pubblica/privata. Questa coppia è nel formato creato `CryptExportKey` dalla funzione Win32. Se `pbKeyBlob` è null, si `szKeyContainer` presuppone che il contenitore di chiavi specificato da contenga la coppia di chiavi.  
  
 `cbKeyBlob`  
 [in] Dimensione, in byte, `pbKeyBlob`di .  
  
 `ppbPublicKeyBlob`  
 [fuori] BLOB della chiave pubblica restituita. Il `ppbPublicKeyBlob` parametro viene allocato da Common Language Runtime e restituito al chiamante. Il chiamante deve liberare la memoria utilizzando il metodo [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) .  
  
 `pcbPublicKeyBlob`  
 [fuori] Dimensione del BLOB della chiave pubblica restituita.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`se il metodo è stato completato correttamente; in caso contrario, un valore HRESULT che indica un errore (vedere [Valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).  
  
## <a name="remarks"></a>Osservazioni  
 La chiave pubblica è contenuta in una struttura [PublicKeyBlob.The public](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) key is contained in a PublicKeyBlob structure.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Struttura PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
