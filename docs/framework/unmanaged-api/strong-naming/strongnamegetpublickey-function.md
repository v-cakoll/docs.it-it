---
title: Funzione StrongNameGetPublicKey
ms.date: 03/30/2017
api_name:
- StrongNameGetPublicKey
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey function [.NET Framework strong naming]
ms.assetid: 5b58c87f-3f72-40df-9b9a-291076931cc3
topic_type:
- apiref
ms.openlocfilehash: fcdd4a3f07b4499fd2388b5d165c409da9150466
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176929"
---
# <a name="strongnamegetpublickey-function"></a>Funzione StrongNameGetPublicKey
Ottiene la chiave pubblica da una coppia di chiavi pubblica/privata. La coppia di chiavi può essere fornita come nome del contenitore di chiavi all'interno di un provider del servizio di crittografia (CSP) o come raccolta non elaborata di byte.  
  
 Questa funzione è deprecata. Utilizzare invece il metodo [ICLRStrongName::StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szKeyContainer`  
 [in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata. Se `pbKeyBlob` è `szKeyContainer` null, è necessario specificare un contenitore valido all'interno del CSP. In questo `StrongNameGetPublicKey` caso, estrae la chiave pubblica dalla coppia di chiavi archiviata nel contenitore.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nell'oggetto binario di grandi dimensioni chiave (BLOB).  
  
 Le chiavi devono essere chiavi di firma RSA (Rivest-Shamir-Adleman) a 1024 bit. Al momento non sono supportati altri tipi di chiavi.  
  
 `pbKeyBlob`  
 [in] Puntatore alla coppia di chiavi pubblica/privata. Questa coppia è nel formato creato `CryptExportKey` dalla funzione Win32. Se `pbKeyBlob` è null, si `szKeyContainer` presuppone che il contenitore di chiavi specificato da contenga la coppia di chiavi.  
  
 `cbKeyBlob`  
 [in] Dimensione, in byte, `pbKeyBlob`di .  
  
 `ppbPublicKeyBlob`  
 [fuori] BLOB della chiave pubblica restituita. Il `ppbPublicKeyBlob` parametro viene allocato da Common Language Runtime e restituito al chiamante. Il chiamante deve liberare la memoria utilizzando la funzione [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)  
  
 `pcbPublicKeyBlob`  
 [fuori] Dimensione del BLOB della chiave pubblica restituita.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al termine del successo; in `false`caso contrario, .  
  
## <a name="remarks"></a>Osservazioni  
 La chiave pubblica è contenuta in una struttura [PublicKeyBlob.The public](publickeyblob-structure.md) key is contained in a PublicKeyBlob structure.  
  
 Se `StrongNameGetPublicKey` la funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** NomeForte.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameGetPublicKey](../hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [Metodo StrongNameTokenFromPublicKey](../hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
- [Struttura PublicKeyBlob](publickeyblob-structure.md)
