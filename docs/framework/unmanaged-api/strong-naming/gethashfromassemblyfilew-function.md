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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d034f15db8f3d452a055c127bb7095667c089ffe
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772044"
---
# <a name="gethashfromassemblyfilew-function"></a>Funzione GetHashFromAssemblyFileW
Ottiene un hash del file di assembly specificato usando l'algoritmo hash specificato. Il percorso del file di assembly deve essere specificato come stringa Unicode.  
  
 Questa funzione è stata deprecata. Usare la [GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md) metodo invece.  
  
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
 [in] Il percorso del file di cui eseguire l'hashing. Questo parametro deve essere una stringa Unicode.  
  
 `piHashAlg`  
 [in, out] Costante che specifica l'algoritmo hash. Usa lo zero per l'algoritmo hash predefinito.  
  
 `pbHash`  
 [out] Il buffer di hash restituito.  
  
 `cchHash`  
 [in] La dimensione massima richiesta del `pbHash`.  
  
 `pchHash`  
 [out] La dimensione restituita, in byte, di `pbHash`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo GetHashFromAssemblyFileW](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfilew-method.md)
- [Metodo GetHashFromAssemblyFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromassemblyfile-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
