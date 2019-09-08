---
title: Funzione StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx function [.NET Framework strong naming]
ms.assetid: 67a8a9f2-dee3-44b2-a1c0-f307a3bdf90f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c000aad12000a9c76fb6dd805a9b002c021be6ef
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798838"
---
# <a name="strongnametokenfromassemblyex-function"></a>Funzione StrongNameTokenFromAssemblyEx
Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica rappresentata dal token.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Percorso del file eseguibile di tipo PE per l'assembly.  
  
 `ppbStrongNameToken`  
 out Token del nome sicuro restituito.  
  
 `pcbStrongNameToken`  
 out Dimensione, in byte, del token del nome sicuro.  
  
 `ppbPublicKeyBlob`  
 out Chiave pubblica restituita.  
  
 `pcbPublicKeyBlob`  
 out Dimensione, in byte, della chiave pubblica.  
  
## <a name="return-value"></a>Valore restituito  
 `true`al completamento; in caso `false`contrario,.  
  
## <a name="remarks"></a>Note  
 Un token di nome sicuro è il formato abbreviato di una chiave pubblica. Il token è un hash a 64 bit creato dalla chiave pubblica usata per firmare l'assembly. Il token fa parte del nome sicuro dell'assembly e può essere letto dai metadati dell'assembly.  
  
 Dopo che la chiave è stata recuperata e il token è stato creato, è necessario chiamare la funzione [StrongNameFreeBuffer](strongnamefreebuffer-function.md) per rilasciare la memoria allocata.  
  
 Se la `StrongNameTokenFromAssemblyEx` funzione non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme** Vedere [Requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria** Incluso come risorsa in mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromAssemblyEx](../hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [Metodo StrongNameTokenFromAssembly](../hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
