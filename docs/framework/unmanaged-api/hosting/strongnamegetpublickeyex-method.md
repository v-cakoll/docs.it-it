---
title: Metodo StrongNameGetPublicKeyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176227"
---
# <a name="strongnamegetpublickeyex-method"></a>Metodo StrongNameGetPublicKeyEx
Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata e specifica un algoritmo hash e un algoritmo di firma.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pwzKeyContainer`  
 [in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata. Se `pbKeyBlob` è `szKeyContainer` null, è necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP). In questo caso, il `StrongNameGetPublicKeyEx` metodo estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.  
  
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
  
 `uHashAlgId`  
 [in] Algoritmo hash dell'assembly. Vedere la sezione Osservazioni per un elenco dei valori accettati.  
  
 `uReserved`  
 [in] Riservato per uso futuro; il valore predefinito è null.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`se il metodo è stato completato correttamente; in caso contrario, un valore HRESULT che indica un errore (vedere [Valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).  
  
## <a name="remarks"></a>Osservazioni  
 La chiave pubblica è contenuta in una struttura [PublicKeyBlob.The public](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) key is contained in a PublicKeyBlob structure.  
  
## <a name="remarks"></a>Osservazioni  
 Nella tabella seguente viene illustrato il `uHashAlgId` set di valori accettati per il parametro.  
  
|Nome|valore|  
|----------|-----------|  
|nessuno|0|  
|SHA-1|0x8004|  
|SHA-256|0x800c|  
|SHA-384|0x800d|  
|SHA-512|0x800e|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Biblioteca:** Incluso come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Struttura PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [Metodo StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
