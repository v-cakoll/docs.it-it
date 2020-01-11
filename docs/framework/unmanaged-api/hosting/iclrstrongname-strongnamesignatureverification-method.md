---
title: Metodo ICLRStrongName::StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerification
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerification method [.NET Framework hosting]
- StrongNameSignatureVerification method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 734dc4d1-0a76-4736-b5ac-cb4253b3dd49
topic_type:
- apiref
ms.openlocfilehash: 6375fd8e4a314403267a4cdf2e8356677e9e7a06
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899494"
---
# <a name="iclrstrongnamestrongnamesignatureverification-method"></a>Metodo ICLRStrongName::StrongNameSignatureVerification
Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Percorso del file eseguibile (con estensione dll o exe) portatile per l'assembly da verificare.  
  
 `dwInFlags`  
 in Flag per modificare il comportamento di verifica. Sono supportati i valori seguenti:  
  
- `SN_INFLAG_FORCE_VER` (0x00000001): impone la verifica anche se è necessario eseguire l'override delle impostazioni del registro di sistema.  
  
- `SN_INFLAG_INSTALL` (0x00000002): specifica che questa è la prima volta che il manifesto viene verificato.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004): specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008): specifica che l'assembly sarà accessibile solo all'utente corrente.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010): specifica che la cache non fornirà alcuna garanzia di restrizione di accesso.  
  
- `SN_INFLAG_RUNTIME` (0x80000000)-riservato per il debug interno.  
  
 `pdwOutFlags`  
 out Flag che indicano se la firma del nome sicuro è stata verificata. È supportato il valore seguente:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001): questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
