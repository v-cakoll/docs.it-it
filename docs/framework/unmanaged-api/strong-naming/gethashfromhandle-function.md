---
title: Funzione GetHashFromHandle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromHandle
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromHandle
helpviewer_keywords: GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ccb6d3b50e70d69b706f63be8a783ad6d7f7cdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromhandle-function"></a>Funzione GetHashFromHandle
Genera un hash per il contenuto del file con l'handle di file specificato, usando l'algoritmo hash specificato.  
  
 Questa funzione è stata deprecata. Utilizzare il [:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `hFile`  
 [in] L'handle del file di cui eseguire l'hashing.  
  
 `piHashAlg`  
 [in, out] Costante che specifica l'algoritmo hash. Utilizzare zero per l'algoritmo predefinito.  
  
 `pbHash`  
 [out] Il buffer di hash restituito.  
  
 `cchHash`  
 [in] La dimensione massima richiesta del `pbHash`.  
  
 `pchHash`  
 [out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [GetHashFromHandle (metodo)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [ICLRStrongName (interfaccia)](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
