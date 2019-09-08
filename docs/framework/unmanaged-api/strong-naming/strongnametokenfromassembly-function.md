---
title: Funzione StrongNameTokenFromAssembly
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssembly
helpviewer_keywords:
- StrongNameTokenFromAssembly function [.NET Framework strong naming]
ms.assetid: 0a4b47ee-02f6-4a98-864e-a6f11ca3f2d9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 71058a1ff82335b2a341904805d06738e662c296
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798867"
---
# <a name="strongnametokenfromassembly-function"></a>Funzione StrongNameTokenFromAssembly
Crea un token con nome sicuro dal file di assembly specificato.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Percorso del file eseguibile di tipo PE per l'assembly.  
  
 `ppbStrongNameToken`  
 out Token del nome sicuro restituito.  
  
 `pcbStrongNameToken`  
 out Dimensione, in byte, del token del nome sicuro.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al completamento; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 Un token di nome sicuro è il formato abbreviato di una chiave pubblica. Il token è un hash a 64 bit creato dalla chiave pubblica usata per firmare l'assembly. Il token fa parte del nome sicuro dell'assembly e può essere letto dai metadati dell'assembly.  
  
 Dopo la creazione del token, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.  
  
 Se la `StrongNameTokenFromAssembly` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [Metodo StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
