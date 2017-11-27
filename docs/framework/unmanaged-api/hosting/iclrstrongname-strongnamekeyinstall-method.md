---
title: Metodo ICLRStrongName::StrongNameKeyInstall
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameKeyInstall
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameKeyInstall
helpviewer_keywords:
- ICLRStrongName::StrongNameKeyInstall method [.NET Framework hosting]
- StrongNameKeyInstall method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 5c15cf3b-164c-49d1-8e57-e42949d55acf
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 241421761b87bf9f3baf7315c2ac8e9ebd499486
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamekeyinstall-method"></a>Metodo ICLRStrongName::StrongNameKeyInstall
Importa una coppia di chiavi pubblica/privata in un contenitore.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameKeyInstall (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszKeyContainer`  
 [in] Il nome del contenitore di chiavi. `wszKeyContainer`deve essere una stringa non vuota.  
  
 `pbKeyBlob`  
 [in] La coppia di chiavi binaria.  
  
 `cbKeyBlob`  
 [in] Le dimensioni, in byte, di `pbKeyBlob`.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Utilizzare il [ICLRStrongName:: StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md) metodo per eliminare il contenitore di chiavi.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [StrongNameKeyDelete (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [ICLRStrongName (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
