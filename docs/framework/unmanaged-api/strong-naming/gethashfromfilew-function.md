---
title: Funzione GetHashFromFileW
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd96b5acb22f63b6e06c981119186680d6593a79
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799191"
---
# <a name="gethashfromfilew-function"></a>Funzione GetHashFromFileW
Genera un hash basato sul contenuto del file specificato da una stringa Unicode.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md) .  
  
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
 in Dimensione massima del buffer a cui `pbHash`punta.  
  
 `pchHash`  
 out Dimensione, in byte, di `pbHash`.  
  
## <a name="remarks"></a>Note  
 Questa funzione è identica a [GetHashFromFile](gethashfromfile-function.md), con la differenza che la specifica del nome file è Unicode anziché ANSI.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromFileW](../hosting/iclrstrongname-gethashfromfilew-method.md)
- [Metodo GetHashFromFile](../hosting/iclrstrongname-gethashfromfile-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
