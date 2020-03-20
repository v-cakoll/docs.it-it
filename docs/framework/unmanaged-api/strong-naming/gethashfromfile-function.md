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
ms.openlocfilehash: ea2b70f37668587fb02513ab54da6c1915e2918d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176981"
---
# <a name="gethashfromfile-function"></a>Funzione GetHashFromFile
Genera un hash basato sul contenuto del file specificato.  
  
 Questa funzione è deprecata. Utilizzare invece il metodo [ICLRStrongName::GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md) .  
  
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
 [in] Nome del file di cui eseguire l'hashing.  
  
 `piHashAlg`  
 [in, out] Algoritmo da utilizzare durante la generazione dell'hash. Gli algoritmi validi sono quelli definiti da Win32 CryptoAPI. Se `piHashAlg` è impostato su 0, viene utilizzato l'algoritmo predefinito CALG_SHA-1.  
  
 `pbHash`  
 [fuori] Matrice di byte contenente l'hash generato.  
  
 `cchHash`  
 [in] Dimensione massima del buffer `pbHash` a cui punta.  
  
 `pchHash`  
 [fuori] Dimensione, in byte, dell'oggetto restituito. `pbHash`  
  
## <a name="remarks"></a>Osservazioni  
 Questa funzione è uguale a [GetHashFromFileW](gethashfromfilew-function.md), con la differenza che la specifica del nome file è ANSI anziché Unicode.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** NomeForte.h  
  
 **Biblioteca:** Incluso come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Metodo GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
