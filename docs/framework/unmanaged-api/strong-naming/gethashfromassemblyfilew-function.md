---
title: Funzione GetHashFromAssemblyFileW
ms.date: 03/30/2017
api_name:
- GetHashFromAssemblyFileW
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromAssemblyFileW
helpviewer_keywords:
- GetHashFromAssemblyFileW function [.NET Framework strong naming]
ms.assetid: d1b2b172-5353-42af-a877-cf653c68ece0
topic_type:
- apiref
ms.openlocfilehash: cf7667f0f2a0f77cd793e00a5de8b030b0c53ec8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140706"
---
# <a name="gethashfromassemblyfilew-function"></a>Funzione GetHashFromAssemblyFileW
Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato. Il percorso del file di assembly deve essere specificato come stringa Unicode.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetHashFromAssemblyFileW (  
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Percorso del file di cui eseguire l'hashing. Questo parametro deve essere una stringa Unicode.  
  
 `piHashAlg`  
 [in, out] Costante che specifica l'algoritmo hash. Usare zero per l'algoritmo hash predefinito.  
  
 `pbHash`  
 out Buffer hash restituito.  
  
 `cchHash`  
 in Dimensioni massime richieste di `pbHash`.  
  
 `pchHash`  
 out Dimensioni restituite, in byte, di `pbHash`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromAssemblyFileW](../hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [Metodo GetHashFromAssemblyFile](../hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
