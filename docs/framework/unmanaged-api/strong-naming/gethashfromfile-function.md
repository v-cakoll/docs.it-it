---
title: Funzione GetHashFromFile
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
- GetHashFromFile
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromFile
helpviewer_keywords:
- GetHashFromFile function [.NET Framework strong naming]
ms.assetid: b3c526a4-8fb4-4ad6-b6af-42ce9c06492e
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: be7979eb0f7d32e02257cc0b3cb400263350f0bd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="gethashfromfile-function"></a>Funzione GetHashFromFile
Genera un hash per il contenuto del file specificato.  
  
 Questa funzione è stata deprecata. Utilizzare il [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHashFromFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,   
    [out] BYTE     *pbHash,      
    [in]  DWORD    cchHash,      
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szFilePath`  
 [in] Il nome del file con hash.  
  
 `piHashAlg`  
 [in, out] L'algoritmo da utilizzare durante la generazione di hash. Gli algoritmi validi sono quelli definiti in CryptoAPI Win32. Se `piHashAlg` è impostato su 0, l'algoritmo predefinito CALG_SHA-1 viene utilizzato.  
  
 `pbHash`  
 [out] Matrice di byte contenente il valore hash generato.  
  
 `cchHash`  
 [in] La dimensione massima del buffer che `pbHash` punta a.  
  
 `pchHash`  
 [out] Le dimensioni, in byte, dell'oggetto restituito `pbHash`.  
  
## <a name="remarks"></a>Note  
 Questa funzione è analoga [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), ad eccezione del fatto che la specifica del nome file è ANSI anziché Unicode.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. H  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Metodo GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)  
 [Metodo GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
