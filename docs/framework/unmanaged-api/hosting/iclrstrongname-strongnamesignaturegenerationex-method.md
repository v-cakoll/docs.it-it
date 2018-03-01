---
title: Metodo ICLRStrongName::StrongNameSignatureGenerationEx
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
- ICLRStrongName.StrongNameSignatureGenerationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureGenerationEx method [.NET Framework hosting]
- StrongNameSignatureGenerationEx method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: c3f34584-c6e2-41fd-bb44-e44da8546309
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247bcfa3c9f7a02dea331ff14948a00812fb06e5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="iclrstrongnamestrongnamesignaturegenerationex-method"></a>Metodo ICLRStrongName::StrongNameSignatureGenerationEx
Genera una firma nome sicuro per l'assembly specificato, in base ai flag specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameSignatureGenerationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob,  
    [in]  DWORD     dwFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Il percorso del file che contiene il manifesto dell'assembly per il quale verrà generata la firma nome sicuro.  
  
 `wszKeyContainer`  
 [in] Il nome del contenitore di chiavi contenente la coppia di chiavi pubblica/privata.  
  
 Se `pbKeyBlob` è null, `wszKeyContainer` deve specificare un contenitore valido all'interno del provider del servizio di crittografia (CSP). In questo caso, la coppia di chiavi archiviata nel contenitore viene utilizzata per firmare il file.  
  
 Se `pbKeyBlob` non è null, si presuppone che la coppia di chiavi deve contenere la chiave BLOB binary large object ().  
  
 `pbKeyBlob`  
 [in] Un puntatore per la coppia di chiavi pubblica/privata. Questa coppia è nel formato creato da Win32 `CryptExportKey` (funzione). Se `pbKeyBlob` è null, il contenitore di chiavi specificato da `wszKeyContainer` si presuppone che la coppia di chiavi.  
  
 `cbKeyBlob`  
 [in] Le dimensioni, in byte, di `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Puntatore alla posizione in cui common language runtime restituisce la firma. Se `ppbSignatureBlob` è null, il runtime archivia la firma nel file specificato da `wszFilePath`.  
  
 Se `ppbSignatureBlob` è non null, common language runtime consente di allocare spazio nel quale restituire la firma. Il chiamante deve liberare questo spazio utilizzando il [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo.  
  
 `pcbSignatureBlob`  
 [out] Le dimensioni in byte, della firma restituita.  
  
 `dwFlags`  
 [in] Uno o più dei seguenti valori:  
  
-   `SN_SIGN_ALL_FILES`(0x00000001) - ricalcola tutti gli hash per i moduli collegati.  
  
-   `SN_TEST_SIGN`(0x00000002) - la firma di test dell'assembly.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Specificare null per `wszFilePath` per calcolare la dimensione della firma senza la creazione della firma.  
  
 La firma possa essere archiviata direttamente nel file o restituita al chiamante.  
  
 Se `SN_SIGN_ALL_FILES` è specificato, ma non è inclusa una chiave pubblica (entrambi `pbKeyBlob` e `wszFilePath` sono null), vengono ricalcolati gli hash per i moduli collegati, ma l'assembly non è firmato.  
  
 Se `SN_TEST_SIGN` viene specificato, l'intestazione di common language runtime non viene modificata per indicare che l'assembly è firmato con un nome sicuro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegeneration-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
