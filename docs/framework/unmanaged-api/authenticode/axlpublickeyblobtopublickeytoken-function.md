---
title: Funzione _AxlPublicKeyBlobToPublicKeyToken
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: _AxlPublicKeyBlobToPublicKeyToken
api_location: clr.dll
api_type: DLLExport
ms.assetid: 2d92a746-d68c-4f53-a16e-727f071a2d80
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7c9dfd42d0908032ed9a652f6f4f5736ba775ce8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="axlpublickeyblobtopublickeytoken-function"></a>Funzione _AxlPublicKeyBlobToPublicKeyToken
Calcola il token di chiave pubblica con nome sicuro da un formato CSP PUBLICKEYBLOB.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT _AxlPublicKeyBlobToPublicKeyToken (  
    [in]  PCCERT_CHAIN_CONTEXT   pCspPublicKeyBlob,  
    [out] LPWSTR                 *ppwszPublicKeyToken  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pCspPublicKeyBlob`  
 [in] BLOB a chiave pubblica CSP.  
  
 `ppwszPublicKeyHash`  
 [out] Puntatore a WCHAR * per ricevere l'hash di chiave pubblica con codifica esadecimale.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la funzione ha esito positivo; in caso contrario, `S_FALSE`.  
  
## <a name="see-also"></a>Vedere anche  
 [Authenticode](../../../../docs/framework/unmanaged-api/authenticode/index.md)
