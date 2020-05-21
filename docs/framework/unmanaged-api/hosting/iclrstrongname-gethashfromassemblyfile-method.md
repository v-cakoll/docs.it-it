---
title: Metodo ICLRStrongName::GetHashFromAssemblyFile
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromAssemblyFile
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromAssemblyFile
helpviewer_keywords:
- ICLRStrongName::GetHashFromAssemblyFile method [.NET Framework hosting]
- GetHashFromAssemblyFile method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 0b67ea03-d474-4605-acaa-57455790250c
topic_type:
- apiref
ms.openlocfilehash: 007de0365bf70b1f4a9a9e0f01807e7fdac19f54
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762149"
---
# <a name="iclrstrongnamegethashfromassemblyfile-method"></a>Metodo ICLRStrongName::GetHashFromAssemblyFile
Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHashFromAssemblyFile (  
    [in]  LPCSTR   szFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szFilePath`  
 in Percorso del file di cui eseguire l'hashing.  
  
 `piHashAlg`  
 [in, out] Costante che specifica l'algoritmo hash. Usare zero per l'algoritmo hash predefinito.  
  
 `pbHash`  
 out Buffer hash restituito.  
  
 `cchHash`  
 in Dimensione massima richiesta di `pbHash` .  
  
 `pchHash`  
 out Dimensione restituita, in byte, di `pbHash` .  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromAssemblyFileW](iclrstrongname-gethashfromassemblyfilew-method.md)
- [Interfaccia ICLRStrongName](iclrstrongname-interface.md)
