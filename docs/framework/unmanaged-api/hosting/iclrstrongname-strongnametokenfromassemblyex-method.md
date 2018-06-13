---
title: Metodo ICLRStrongName::StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a5bb3d48d33333e888200bc607d3a193482f0336
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433653"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a>Metodo ICLRStrongName::StrongNameTokenFromAssemblyEx
Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica che rappresenta il token.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Il percorso del file eseguibile portabile (PE) per l'assembly.  
  
 `ppbStrongNameToken`  
 [out] Il token restituito con nome sicuro.  
  
 `pcbStrongNameToken`  
 [out] Le dimensioni in byte, del token con nome sicuro.  
  
 `ppbPublicKeyBlob`  
 [out] La chiave pubblica restituita.  
  
 `pcbPublicKeyBlob`  
 [out] Le dimensioni in byte, della chiave pubblica.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Un token con nome sicuro è la forma abbreviata di una chiave pubblica. Il token è un hash a 64 bit che viene creato dalla chiave pubblica utilizzata per firmare l'assembly. Il token fa parte del nome sicuro per l'assembly e può essere letti dai metadati dell'assembly.  
  
 Dopo il recupero della chiave e il token viene creato, è necessario chiamare il [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo per rilasciare la memoria allocata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameTokenFromAssembly](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
