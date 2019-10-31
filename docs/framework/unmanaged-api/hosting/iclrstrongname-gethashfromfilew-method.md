---
title: Metodo ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
ms.openlocfilehash: 553acc178bc5805b5afef5931fefc8ad74cbac39
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135179"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a>Metodo ICLRStrongName::GetHashFromFileW
Genera un hash basato sul contenuto del file specificato da una stringa Unicode.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Nome Unicode del file di cui eseguire l'hashing.  
  
 `piHashAlg`  
 [in, out] Algoritmo da utilizzare durante la generazione dell'hash. Gli algoritmi validi sono quelli definiti dalla CryptoAPI Win32. Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.  
  
 `pbHash`  
 out Matrice di byte contenente l'hash generato.  
  
 `cchHash`  
 in Dimensione massima del buffer a cui punta `pbHash`.  
  
 `pchHash`  
 out Dimensione, in byte, del `pbHash`.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Questo metodo è uguale al metodo [ICLRStrongName:: GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) , ad eccezione del fatto che la specifica del nome file è Unicode anziché ANSI.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
