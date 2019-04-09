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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0e7df65c28fad6fa79ec7a18d8511955330b2817
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59227743"
---
# <a name="strongnamesignaturegeneration-function"></a>Funzione StrongNameSignatureGeneration
Genera una firma con nome sicuro per l'assembly specificato.  
  
 Questa funzione è stata deprecata. Usare la [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Il percorso del file che contiene il manifesto dell'assembly per le quali verrà generata la firma con nome sicuro.  
  
 `wszKeyContainer`  
 [in] Il nome del contenitore di chiavi che contiene la coppia di chiavi pubblica/privata.  
  
 Se `pbKeyBlob` è null, `wszKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP). In questo caso, la coppia di chiavi archiviata nel contenitore viene usata per firmare il file.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().  
  
 Le chiavi devono essere Rivest-Shamir-Adleman (RSA di 1024 bit) le chiavi di firma. Nessun altro tipo di chiavi è supportato in questo momento.  
  
 `pbKeyBlob`  
 [in] Un puntatore per la coppia di chiavi pubblica/privata. Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione). Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `wszKeyContainer` si presuppone che contenga la coppia di chiavi.  
  
 `cbKeyBlob`  
 [in] Le dimensioni, in byte, di `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Puntatore alla posizione in cui common language runtime restituisce la firma. Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.  
  
 Se `ppbSignatureBlob` è non null, common language runtime alloca spazio in cui si desidera ottenere la firma. Il chiamante deve liberare questo spazio usando il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/strong-naming/strongnamefreebuffer-function.md) (funzione).  
  
 `pcbSignatureBlob`  
 [out] Le dimensioni, in byte, della firma restituita.  
  
## <a name="return-value"></a>Valore restituito  
 `true` al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Specificare null per `wszFilePath` per calcolare le dimensioni della firma senza la creazione della firma.  
  
 La firma possa essere archiviati utilizzando direttamente il file o restituito al chiamante.  
  
 Se il `StrongNameSignatureGeneration` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) funzione per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)
- [Metodo StrongNameSignatureGenerationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
