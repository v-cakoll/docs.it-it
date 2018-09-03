---
title: Metodo StrongNameSignatureVerificationEx2
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameSignatureVerificationEx2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameSignatureVerificationEx2
helpviewer_keywords:
- StrongNameSignatureVerificationEx2 method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameSignatureVerificationEx2 method [.NET Framework hosting]
ms.assetid: dfd4133f-a074-4db3-a7ee-4f250fe9ad3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e47c2ac69317b2d2db489dce9a0102b5fe304c05
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2018
ms.locfileid: "43483055"
---
# <a name="strongnamesignatureverificationex2-method"></a>Metodo StrongNameSignatureVerificationEx2
Verifica la firma di un assembly con nome sicuro e fornisce un mapping tra la chiave ECMA e una chiave reale.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,    [in]  BYTE      *pbEcmaPublicKey,  
    [in]  DWORD     cbEcmaPublicKey,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Il percorso del file di (.exe o DLL) eseguibile portabile per l'assembly da verificare.  
  
 `fForceVerification`  
 [in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema; in caso contrario, `false`.  
  
 `pbEcmaPublicKey`  
 [in] Un puntatore per il mapping dalla chiave pubblica ECMA per il tasto effettivo usato per la verifica.  
  
 `cbEcmaPublicKey`  
 [in] La lunghezza della chiave pubblica reale ECMA.  
  
 `pfWasVerified`  
 [out] `true` se la firma con nome sicuro è stato verificato; in caso contrario, `false`. Questo parametro viene impostato anche su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del Registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` Se la verifica ha avuto esito positivo. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [Metodo StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
