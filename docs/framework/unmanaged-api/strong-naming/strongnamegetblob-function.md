---
title: Funzione StrongNameGetBlob
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
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b1948a0d8a8536ebe9b0531eecaf3df446252b0a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="strongnamegetblob-function"></a>Funzione StrongNameGetBlob
Riempie il buffer specificato con la rappresentazione binaria del file eseguibile all'indirizzo specificato.  
  
 Questa funzione è stata deprecata. Utilizzare il [:: StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Un percorso valido per il file eseguibile da caricare.  
  
 `pbBlob`  
 [in] Buffer in cui caricare il file eseguibile.  
  
 `pcbBlob`  
 [in, out] La richiesta di dimensione massima, in byte, di `pbBlob`. Al momento della restituzione, le dimensioni effettive, in byte, di `pbBlob`.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al termine dell'esecuzione; in caso contrario, `false`.  
  
## <a name="remarks"></a>Note  
 Se il `StrongNameGetBlob` funzione non viene completata correttamente, chiamare il [StrongNameErrorInfo](../../../../docs/framework/unmanaged-api/strong-naming/strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo StrongNameGetBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblob-method.md)  
 [Metodo StrongNameGetBlobFromImage](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetblobfromimage-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
