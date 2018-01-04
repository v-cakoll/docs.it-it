---
title: Funzione StrongNameSignatureVerificationFromImage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameSignatureVerificationFromImage
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameSignatureVerificationFromImage
helpviewer_keywords: StrongnameSignatureVerificationFromImage function [.NET Framework strong naming]
ms.assetid: 9fb144d2-07e0-4a0e-8e05-907bbb6c9e03
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 178dcbae4f8ec40ac9ef14fc00109c83ab87c21a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamesignatureverificationfromimage-function"></a>Funzione StrongNameSignatureVerificationFromImage
Verifica che un assembly che è già stato mappato alla memoria sia valido per la chiave pubblica associata.  
  
 Questa funzione è stata deprecata. Utilizzare il [:: StrongNameVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEAN StrongNameSignatureVerificationFromImage (  
    [in]  BYTE    *pbBase,  
    [in]  DWORD   dwLength,  
    [in]  DWORD   dwInFlags,  
    [out] DWORD   *pdwOutFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbBase`  
 [in] L'indirizzo virtuale relativo del manifesto dell'assembly mappato.  
  
 `dwLength`  
 [in] Le dimensioni in byte, dell'immagine mappata.  
  
 `dwInFlags`  
 [in] Flag che influenzano il comportamento di verifica. Sono supportati i seguenti valori:  
  
-   `SN_INFLAG_FORCE_VER`(0x00000001) - impone la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema.  
  
-   `SN_INFLAG_INSTALL`(0x00000002) - specifica che questa è la prima verifica eseguita in questa immagine.  
  
-   `SN_INFLAG_ADMIN_ACCESS`(0x00000004) - specifica che la cache verrà concesso l'accesso solo agli utenti che dispongono di privilegi amministrativi.  
  
-   `SN_INFLAG_USER_ACCESS`(0x00000008) - specifica che l'assembly sarà accessibili solo all'utente corrente.  
  
-   `SN_INFLAG_ALL_ACCESS`(0x00000010) - specifica che la cache non fornirà alcuna garanzia di restrizione dell'accesso.  
  
-   `SN_INFLAG_RUNTIME`(0x80000000) - riservato per il debug interno.  
  
 `pdwOutFlags`  
 [out] Flag per informazioni aggiuntive sull'output. È supportato il valore seguente:  
  
-   `SN_OUTFLAG_WAS_VERIFIED`(0x00000001) - questo valore è impostato su `false` per specificare che la verifica ha avuto esito positivo a causa delle impostazioni del Registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Se il `StrongNameSignatureVerificationFromImage` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in mscoree.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameSignatureVerificationFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationfromimage-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
