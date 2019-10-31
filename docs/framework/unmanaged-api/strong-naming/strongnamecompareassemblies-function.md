---
title: Funzione StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameCompareAssemblies
helpviewer_keywords:
- StrongNameCompareAssemblies function [.NET Framework strong naming]
ms.assetid: 763f2375-efc6-4219-8806-a3b0567ef72b
topic_type:
- apiref
ms.openlocfilehash: adde52dddb63b83dcd7ff10703a43928d9601c92
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140629"
---
# <a name="strongnamecompareassemblies-function"></a>Funzione StrongNameCompareAssemblies
Determina se due assembly differiscono solo per le firme con nome sicuro.  
  
 Questa funzione è stata deprecata. Usare invece il metodo [ICLRStrongName:: StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md) .  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
BOOLEAN StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszAssembly1`  
 in Percorso del primo assembly.  
  
 `wszAssembly2`  
 in Percorso del secondo assembly.  
  
 `pdwResult`  
 out Uno dei valori seguenti:  
  
- `SN_CMP_DIFFERENT` (0): specifica che gli assembly contengono dati diversi.  
  
- `SN_CMP_IDENTICAL` (1): specifica che gli assembly sono esattamente uguali, incluse le relative firme e checksum.  
  
- `SN_CMP_SIGONLY` (2): specifica che gli assembly differiscono solo per la firma e il checksum.  
  
## <a name="return-value"></a>Valore restituito  
 `true` al completamento; in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** StrongName. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="remarks"></a>Note  
 La firma con nome sicuro di un assembly è costituita dal nome del testo, dalla versione, dalle impostazioni cultura e dal token di chiave pubblica dell'assembly.  
  
 Se la funzione `StrongNameCompareAssemblies` non viene completata correttamente, chiamare la funzione [StrongNameErrorInfo](strongnameerrorinfo-function.md) per recuperare l'ultimo errore generato.  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameCompareAssemblies](../hosting/iclrstrongname-strongnamecompareassemblies-method.md)
- [Interfaccia ICLRStrongName](../hosting/iclrstrongname-interface.md)
