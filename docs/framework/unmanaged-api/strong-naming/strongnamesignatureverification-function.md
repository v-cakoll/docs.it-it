---
title: Funzione StrongNameSignatureVerification
ms.date: 03/30/2017
api_name:
- StrongNameSignatureVerification
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameSignatureVerification
helpviewer_keywords:
- StrongNameSignatureVerification function [.NET Framework strong naming]
ms.assetid: 933758dd-231e-4382-8819-242c0a13a4b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3209b42263c62c8296d43ab06b0d89db2dd89be8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665984"
---
# <a name="strongnamesignatureverification-function"></a>Funzione StrongNameSignatureVerification
Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro, che viene verificata in base ai flag specificati.  
  
 Questa funzione è stata deprecata. Usare la [StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) metodo invece.  
  
## <a name="syntax"></a>Sintassi  
  
```  
BOOLEAN StrongNameSignatureVerification (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  DWORD     dwInFlags,  
    [out] DWORD     *pdwOutFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Il percorso del file di (con estensione dll o .exe) eseguibile portabile per l'assembly da verificare.  
  
 `dwInFlags`  
 [in] Flag per modificare il comportamento di verifica. Sono supportati i valori seguenti:  
  
- `SN_INFLAG_FORCE_VER` (0x00000001) - forza la verifica, anche se è necessario eseguire l'override delle impostazioni del Registro di sistema.  
  
- `SN_INFLAG_INSTALL` (0x00000002): Specifica che questa è la prima volta che viene verificato il manifesto.  
  
- `SN_INFLAG_ADMIN_ACCESS` (0x00000004): Specifica che la cache consentirà l'accesso solo agli utenti che dispongono di privilegi amministrativi.  
  
- `SN_INFLAG_USER_ACCESS` (0x00000008): Specifica che l'assembly è accessibile solo all'utente corrente.  
  
- `SN_INFLAG_ALL_ACCESS` (0x00000010): Specifica che la cache non fornirà offre alcuna garanzia di limitazione dell'accesso.  
  
- `SN_INFLAG_RUNTIME` (0x80000000) - riservato per il debug interno.  
  
 `pdwOutFlags`  
 [out] Flag che indica se è stata verificata la firma con nome sicuro. È supportato il valore seguente:  
  
- `SN_OUTFLAG_WAS_VERIFIED` (0x00000001) - questo valore è impostato su `false` per specificare che la verifica è riuscita a causa delle impostazioni del Registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `true` Se la verifica ha avuto esito positivo. in caso contrario, `false`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** StrongName.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Metodo StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
