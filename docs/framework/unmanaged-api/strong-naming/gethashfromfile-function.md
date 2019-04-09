---
title: Funzione GetHashFromFile
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5774b7cdcfedfc407b626ab5052f5b4a77461e9b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155909"
---
# <a name="gethashfromfile-function"></a>Funzione GetHashFromFile
Genera un hash basato sul contenuto del file specificato.  
  
 Questa funzione è stata deprecata. Usare la [GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) metodo invece.  
  
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
  
## <a name="parameters"></a>Parametri  
 `szFilePath`  
 [in] Il nome del file da hash.  
  
 `piHashAlg`  
 [in, out] L'algoritmo da utilizzare durante la generazione di hash. Gli algoritmi validi sono quelli definiti per la funzione CryptoAPI Win32. Se `piHashAlg` è impostato su 0, l'algoritmo predefinito viene utilizzato CALG_SHA-1.  
  
 `pbHash`  
 [out] Matrice di byte contenente il valore hash generato.  
  
 `cchHash`  
 [in] Le dimensioni massime del buffer che `pbHash` punta a.  
  
 `pchHash`  
 [out] Le dimensioni, in byte, del valore restituito `pbHash`.  
  
## <a name="remarks"></a>Note  
 Questa funzione equivale [GetHashFromFileW](../../../../docs/framework/unmanaged-api/strong-naming/gethashfromfilew-function.md), ad eccezione del fatto che la specifica del nome file è ANSI invece di Unicode.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [Metodo GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
