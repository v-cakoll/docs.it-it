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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: de4e55c8e1a13daf07a8a75a19a44127779d5c05
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481612"
---
# <a name="iclrstrongnamestrongnamecompareassemblies-method"></a>Metodo ICLRStrongName::StrongNameCompareAssemblies
Determina se due assembly differiscono solo per le firme con nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameCompareAssemblies (  
    [in]  LPCWSTR   wszAssembly1,  
    [in]  LPCWSTR   wszAssembly2,  
    [out] DWORD     *pdwResult  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszAssembly1`  
 [in] Il percorso dell'assembly prima.  
  
 `wszAssembly2`  
 [in] Il percorso dell'assembly di secondo.  
  
 `pdwResult`  
 [out] Uno dei valori seguenti:  
  
-   `SN_CMP_DIFFERENT` (0): Specifica che gli assembly contengono dati diversi.  
  
-   `SN_CMP_IDENTICAL` (1): Specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.  
  
-   `SN_CMP_SIGONLY` (2): Specifica che gli assembly si differenziano solo per la firma e checksum.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Note  
 La firma con nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
