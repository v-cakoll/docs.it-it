---
title: Funzione StrongNameKeyInstall
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: StrongNameKeyInstall
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: StrongNameKeyInstall
helpviewer_keywords: StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 60044e12a884a28cb7485118a95d2bf7650723fe
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="strongnamekeyinstall-function"></a>Funzione StrongNameKeyInstall
Importa una coppia di chiavi pubblica/privata in un contenitore.  
  
 Questa funzione è stata deprecata. Utilizzare il [ICLRStrongName:: StrongNameKeyInstall](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEAN StrongNameKeyInstall (  
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
 `true`al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Utilizzare il [StrongNameKeyDelete](../../../../docs/framework/unmanaged-api/strong-naming/strongnamekeydelete-function.md) funzione per eliminare il contenitore di chiavi.  
  
 Se il `StrongNameKeyInstall` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [StrongNameKeyInstall (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeyinstall-method.md)  
 [StrongNameKeyDelete (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeydelete-method.md)  
 [ICLRStrongName (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
