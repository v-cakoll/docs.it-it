---
title: Metodo ICLRStrongName::StrongNameSignatureVerificationEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureVerificationEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureVerificationEx
helpviewer_keywords:
- StrongNameSignatureVerificationEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureVerificationEx method [.NET Framework hosting]
ms.assetid: dbd2f662-208b-4174-b301-5c99af91040f
topic_type:
- apiref
ms.openlocfilehash: 3e4181cbd14674336133314acdcd6cdcf0c9ff6b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134925"
---
# <a name="iclrstrongnamestrongnamesignatureverificationex-method"></a>Metodo ICLRStrongName::StrongNameSignatureVerificationEx
Ottiene un valore che indica se il manifesto dell'assembly nel percorso specificato contiene una firma con nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameSignatureVerificationEx (  
    [in]  LPCWSTR   wszFilePath,  
    [in]  BOOLEAN   fForceVerification,  
    [out] BOOLEAN   *pfWasVerified  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszFilePath`  
 in Percorso del file eseguibile (exe o dll) portatile per l'assembly da verificare.  
  
 `fForceVerification`  
 [in] `true` per eseguire la verifica, anche se è necessario eseguire l'override delle impostazioni del registro di sistema; in caso contrario, `false`.  
  
 `pfWasVerified`  
 [out] `true` se la firma del nome sicuro è stata verificata. in caso contrario, `false`. `pfWasVerified` viene inoltre impostata su `false` se la verifica ha avuto esito positivo a causa delle impostazioni del registro di sistema.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se la verifica ha avuto esito positivo; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Il metodo [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) fornisce una funzionalità simile al metodo [ICLRStrongName:: StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md) . Tuttavia, il secondo parametro di input e il parametro di output per [ICLRStrongName:: StrongNameSignatureVerificationEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverificationex-method.md) sono di tipo `BOOLEAN` anziché `DWORD`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameSignatureVerification](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignatureverification-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
