---
title: Metodo ICLRStrongName::StrongNameCompareAssemblies
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameCompareAssemblies
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameCompareAssemblies
helpviewer_keywords:
- ICLRStrongName::StrongNameCompareAssemblies method [.NET Framework hosting]
- StrongNameCompareAssemblies method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: b1fb356c-72cf-4aa4-8376-f291a6d97c01
topic_type:
- apiref
ms.openlocfilehash: fdca03b781e07b709cbc54e673dbaa2a1130fbe3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73135154"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>Metodo ICLRStrongName::StrongNameCompareAssemblies
Determina se due assembly differiscono solo per le firme con nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameCompareAssemblies (  
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
 `S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Note  
 La firma con nome sicuro di un assembly è costituita dal nome del testo, dalla versione, dalle impostazioni cultura e dal token di chiave pubblica dell'assembly.  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
