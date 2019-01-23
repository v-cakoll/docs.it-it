---
title: Metodo ICLRStrongName::GetHashFromFileW
ms.date: 03/30/2017
api_name:
- ICLRStrongName.GetHashFromFileW
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::GetHashFromFileW
helpviewer_keywords:
- GetHashFromFileW method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::GetHashFromFileW method [.NET Framework hosting]
ms.assetid: c6ff45fc-905d-4c6e-b00c-97c6c7c55d99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e2ca00b660a9cbb408fd1175e94a4242dae5f1a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54523961"
---
# <a name="iclrstrongnamegethashfromfilew-method"></a>Metodo ICLRStrongName::GetHashFromFileW
Genera un hash basato sul contenuto del file specificato da una stringa Unicode.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetHashFromFileW (   
    [in]  LPCWSTR   wszFilePath,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE      *pbHash,  
    [in]  DWORD     cchHash,  
    [out] DWORD     *pchHash  
);   
```  
  
#### <a name="parameters"></a>Parametri  
 `wszFilePath`  
 [in] Il nome di Unicode del file da hash.  
  
 `piHashAlg`  
 [in, out] L'algoritmo da utilizzare durante la generazione di hash. Gli algoritmi validi sono quelli definiti per la funzione CryptoAPI Win32. Se `piHashAlg` è impostato su 0, l'algoritmo predefinito viene utilizzato CALG_SHA-1.  
  
 `pbHash`  
 [out] Matrice di byte contenente il valore hash generato.  
  
 `cchHash`  
 [in] Le dimensioni massime del buffer a cui punta `pbHash`.  
  
 `pchHash`  
 [out] Le dimensioni, in byte, di `pbHash`.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Questo metodo è quello utilizzato per il [GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md) metodo, ad eccezione del fatto che il nome del file specifica è Unicode anziché ANSI.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Metodo GetHashFromFile](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromfile-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
