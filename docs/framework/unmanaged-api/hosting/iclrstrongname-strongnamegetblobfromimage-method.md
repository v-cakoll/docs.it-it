---
title: Metodo ICLRStrongName::StrongNameGetBlobFromImage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameGetBlobFromImage
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetBlobFromImage method [.NET Framework hosting]
ms.assetid: 0f5a2ec8-e776-4fd8-bda6-937b6834575a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 80edfa333f73854869c3fa6786e038c796b09087
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamegetblobfromimage-method"></a>Metodo ICLRStrongName::StrongNameGetBlobFromImage
Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameGetBlobFromImage (  
    [in]  BYTE        *pbBase,  
    [in]  DWORD       dwLength,  
    [in]  BYTE        *pbBlob,  
    [in, out] DWORD   *pcbBlob  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `pbBase`  
 [in] L'indirizzo di memoria del manifesto dell'assembly mappato.  
  
 `dwLength`  
 [in] Le dimensioni, in byte, dell'immagine in `pbBase`.  
  
 `pbBlob`  
 [in] Un buffer che deve contenere la rappresentazione binaria dell'immagine.  
  
 `pcbBlob`  
 [in, out] La richiesta di dimensione massima, in byte, di `pbBlob`. Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [StrongNameGetBlob (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [ICLRStrongName (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
