---
title: Metodo ICLRStrongName::GetHashFromFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromFile method [.NET Framework hosting]
- GetHashFromFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 9e50480a-8ada-4044-b2a5-97bb14ed3525
topic_type:
- apiref
ms.openlocfilehash: 798bb0585bfe4cc29afba2fbefae818301704613
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135185"
---
# <a name="iclrstrongnamegethashfromfile-method"></a>Metodo ICLRStrongName::GetHashFromFile
Genera un hash basato sul contenuto del file specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Nome del file di cui eseguire l'hashing.  
  
 `piHashAlg`  
 [in, out] Algoritmo da utilizzare durante la generazione dell'hash. Gli algoritmi validi sono quelli definiti dalla CryptoAPI Win32. Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.  
  
 `pbHash`  
 out Matrice di byte contenente l'hash generato.  
  
 `cchHash`  
 in Dimensione massima del buffer a cui punta il `pbHash`.  
  
 `pchHash`  
 out Dimensione, in byte, dell'oggetto restituito `pbHash`.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Questo metodo è uguale al metodo [ICLRStrongName:: GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md) , ad eccezione del fatto che la specifica del nome file è ANSI anziché Unicode.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfilew-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
