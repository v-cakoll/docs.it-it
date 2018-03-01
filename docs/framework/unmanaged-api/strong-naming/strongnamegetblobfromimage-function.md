---
title: Funzione StrongNameGetBlobFromImage
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- StrongNameGetBlobFromImage
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlobFromImage
helpviewer_keywords:
- StrongNameGetBlobFromImage function [.NET Framework strong naming]
ms.assetid: 1de658e6-da32-4d01-9097-6f43c92222e1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3dd5fa1838517baa97079f5d7f75a789384255a2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetblobfromimage-function"></a>Funzione StrongNameGetBlobFromImage
Ottiene una rappresentazione binaria dell'immagine di assembly in corrispondenza dell'indirizzo di memoria specificata.  
  
 Questa funzione è stata deprecata. Utilizzare il [:: StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEAN StrongNameGetBlobFromImage (  
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
 `true`al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Se il `StrongNameGetBlobFromImage` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [Metodo StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
