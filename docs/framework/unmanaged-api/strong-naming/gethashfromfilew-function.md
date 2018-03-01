---
title: Funzione GetHashFromFileW
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
- GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW function [.NET Framework strong naming]
ms.assetid: 97c2d7a6-5376-45a1-ba65-146a249147cc
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: d7d62526a6ac9bb06a7de8287c9687933402bfb8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromfilew-function"></a>Funzione GetHashFromFileW
Genera un hash per il contenuto del file specificato da una stringa Unicode.  
  
 Questa funzione è stata deprecata. Utilizzare il [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Nome del file hash Unicode.  
  
 `piHashAlg`  
 [in, out] L'algoritmo da utilizzare durante la generazione di hash. Gli algoritmi validi sono quelli definiti in CryptoAPI Win32. Se `piHashAlg` è impostato su 0, l'algoritmo predefinito CALG_SHA-1 viene utilizzato.  
  
 `pbHash`  
 [out] Matrice di byte contenente il valore hash generato.  
  
 `cchHash`  
 [in] La dimensione massima del buffer a cui puntava `pbHash`.  
  
 `pchHash`  
 [out] Le dimensioni, in byte, di `pbHash`.  
  
## <a name="remarks"></a>Note  
 Questa funzione è analoga [GetHashFromFile](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfile-function.md), ad eccezione del fatto che la specifica del nome di file in formato Unicode anziché ANSI.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [Metodo GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
