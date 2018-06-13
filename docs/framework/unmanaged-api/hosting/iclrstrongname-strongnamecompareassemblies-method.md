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
ms.openlocfilehash: c5020c31f590f527856f966ede512e98c07496ac
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435388"
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
  
#### <a name="parameters"></a>Parametri  
 `wszAssembly1`  
 [in] Il percorso del primo assembly.  
  
 `wszAssembly2`  
 [in] Il percorso per il secondo assembly.  
  
 `pdwResult`  
 [out] Uno dei valori seguenti:  
  
-   `SN_CMP_DIFFERENT` (0): Specifica che l'assembly deve contenere dati diversi.  
  
-   `SN_CMP_IDENTICAL` (1) - specifica che gli assembly sono esattamente uguali, comprese le firme e checksum.  
  
-   `SN_CMP_SIGONLY` (2) - specifica che gli assembly si differenziano solo per la firma e checksum.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` Se il metodo viene completato correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](http://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. H  
  
 **Libreria:** inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="remarks"></a>Note  
 La firma nome sicuro di un assembly è costituito da testo Nome, versione, impostazioni cultura e token di chiave pubblica dell'assembly.  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
