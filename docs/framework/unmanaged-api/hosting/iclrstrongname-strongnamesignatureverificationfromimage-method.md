---
title: Metodo ICLRStrongName::StrongNameSignatureVerificationFromImage
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationFromImage
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureVerificationFromImage method [.NET Framework hosting]
- StrongNameSignatureVerificationFromImage method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: da91c138-ee30-4fd4-a040-464d97d7e41a
topic_type:
- apiref
ms.openlocfilehash: 1bfc41fdad35a7e0560d251179ea035c96aecab7
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/11/2020
ms.locfileid: "75899525"
---
# <a name="iclrstrongnamestrongnamesignatureverificationfromimage-method"></a>Metodo ICLRStrongName::StrongNameSignatureVerificationFromImage
Verifica che un assembly di cui è già stato eseguito il mapping in memoria sia valido per la chiave pubblica associata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pbBase`  
 in Indirizzo virtuale relativo del manifesto dell'assembly mappato.  
  
 `dwLength`  
 in Dimensione, in byte, dell'immagine mappata.  
  
 `dwInFlags`  
 in Flag che influenzano il comportamento di verifica. Sono supportati i valori seguenti:  
  
- `SN_INFLAG_FORCE_VER` (0x00000001): impone la verifica anche se è necessario eseguire l'override delle impostazioni del registro di sistema.  
  
- `SN_INFLAG_INSTALL` (0x00000002): specifica che si tratta della prima verifica eseguita su questa immagine.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004): specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008): specifica che l'assembly sarà accessibile solo all'utente corrente.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010): specifica che la cache non fornirà alcuna garanzia di restrizione di accesso.  
  
- `SN_INFLAG_RUNTIME` (0x80000000)-riservato per il debug interno.  
  
 `pdwOutFlags`  
 out Flag per informazioni aggiuntive sull'output. È supportato il valore seguente:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001): questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).  
  
## <a name="requirements"></a>Requisiti di  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
