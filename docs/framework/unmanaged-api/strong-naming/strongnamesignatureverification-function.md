---
title: Funzione StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c888c32a0b40d2458a919613e35ca9d1d830c4f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="strongnamesignatureverification-function"></a>Funzione StrongNameSignatureVerification
Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma nome sicuro, che viene verificata in base ai flag specificati.  
  
 Questa funzione è stata deprecata. Utilizzare il [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Il percorso al portatile (. dll o .exe) file eseguibile per l'assembly verificare.  
  
 `dwInFlags`  
 [in] Flag per modificare il comportamento di verifica. Sono supportati i seguenti valori:  
  
-   `SN_INFLAG_FORCE_VER` (0x00000001) - impone la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema.  
  
-   `SN_INFLAG_INSTALL` (0x00000002) - specifica che questa è la prima volta che il manifesto viene verificato.  
  
-   `SN_INFLAG_ADMIN_ACCESS` (0x00000004) - specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.  
  
-   `SN_INFLAG_USER_ACCESS` (0x00000008) - specifica che l'assembly sarà accessibili solo all'utente corrente.  
  
-   `SN_INFLAG_ALL_ACCESS` (0x00000010) - specifica che la cache non fornirà alcuna garanzia di restrizione dell'accesso.  
  
-   `SN_INFLAG_RUNTIME` (0x80000000) - riservato per il debug interno.  
  
 `pdwOutFlags`  
 [out] Flag che indica se è stata verificata la firma nome sicuro. È supportato il valore seguente:  
  
-   `SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del Registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `true` Se la verifica ha avuto esito positivo. in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)  
 [Metodo StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
