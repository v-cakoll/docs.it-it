---
title: Funzione StrongNameSignatureGeneration
ms.date: 03/30/2017
api_name:
- StrongNameSignatureGeneration
api_location:
- mscoree.dll
- mscorsn.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration function [.NET Framework strong naming]
ms.assetid: 839b765c-3e41-44ce-bf1b-dc10453db18e
ms.openlocfilehash: d7f481e5c61ec65d2e7414bd47227866f3435028
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176903"
---
# <a name="strongnamesignaturegeneration-function"></a>Funzione StrongNameSignatureGeneration
Genera una firma con nome sicuro per l'assembly specificato.  
  
 Questa funzione è deprecata. Utilizzare invece il metodo [ICLRStrongName::StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameSignatureGeneration (
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Percorso del file che contiene il manifesto dell'assembly per il quale verrà generata la firma con nome sicuro.  
  
 `wszKeyContainer`  
 [in] Nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.  
  
 Se `pbKeyBlob` è `wszKeyContainer` null, è necessario specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP). In questo caso, la coppia di chiavi archiviata nel contenitore viene utilizzata per firmare il file.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi sia contenuta nell'oggetto binario di grandi dimensioni chiave (BLOB).  
  
 Le chiavi devono essere chiavi di firma RSA (Rivest-Shamir-Adleman) a 1024 bit. Al momento non sono supportati altri tipi di chiavi.  
  
 `pbKeyBlob`  
 [in] Puntatore alla coppia di chiavi pubblica/privata. Questa coppia è nel formato creato `CryptExportKey` dalla funzione Win32. Se `pbKeyBlob` è null, si `wszKeyContainer` presuppone che il contenitore di chiavi specificato da contenga la coppia di chiavi.  
  
 `cbKeyBlob`  
 [in] Dimensione, in byte, `pbKeyBlob`di .  
  
 `ppbSignatureBlob`  
 [fuori] Puntatore al percorso in cui Common Language Runtime restituisce la firma. Se `ppbSignatureBlob` è null, il runtime archivia `wszFilePath`la firma nel file specificato da .  
  
 Se `ppbSignatureBlob` non è null, Common Language Runtime alloca lo spazio in cui restituire la firma. Il chiamante deve liberare questo spazio utilizzando la funzione [StrongNameFreeBuffer.](strongnamefreebuffer-function.md)  
  
 `pcbSignatureBlob`  
 [fuori] Dimensione, in byte, della firma restituita.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al termine del successo; in `false`caso contrario, .  
  
## <a name="remarks"></a>Osservazioni  
 Specificare `wszFilePath` null per calcolare la dimensione della firma senza creare la firma.  
  
 La firma può essere archiviata direttamente nel file o restituita al chiamante.  
  
 Se `StrongNameSignatureGeneration` la funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** NomeForte.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameSignatureGeneration](../hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Metodo StrongNameSignatureGenerationEx](../hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
