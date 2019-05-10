---
title: Metodo ICLRStrongName::StrongNameKeyGen
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameKeyGen
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameKeyGen
helpviewer_keywords:
- StrongNameKeyGen method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameKeyGen method [.NET Framework hosting]
ms.assetid: ac5c1245-9acf-4271-9c08-3d9b7c670df3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a70a23e6c6e219b76ccfee6cecdccf7ed0533e75
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64584614"
---
# <a name="iclrstrongnamestrongnamekeygen-method"></a>Metodo ICLRStrongName::StrongNameKeyGen
Crea una nuova coppia di chiavi pubblica/privata per l'uso come nome sicuro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT StrongNameKeyGen (  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  DWORD     dwFlags,  
    [out] BYTE      **ppbKeyBlob,  
    [out] ULONG     *pcbKeyBlob  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `wszKeyContainer`  
 [in] Il nome di contenitore di chiavi richiesto. `wszKeyContainer` deve essere una stringa non vuota o null per generare un nome temporaneo.  
  
 `dwFlags`  
 [in] Un valore che specifica se lasciare la chiave di registrazione. Sono supportati i valori seguenti:  
  
- 0x00000000 - utilizzato quando `wszKeyContainer` è null per generare un nome di contenitore di chiavi temporanee.  
  
- 0x00000001 (`SN_LEAVE_KEY`): Specifica che la chiave deve essere registrata a sinistra.  
  
 `ppbKeyBlob`  
 [out] La coppia di chiavi pubblica/privata restituita.  
  
 `pcbKeyBlob`  
 [out] Le dimensioni, in byte, di `ppbKeyBlob`.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` Se il metodo è stata completata correttamente. in caso contrario, un valore HRESULT indicante un errore (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="remarks"></a>Note  
 Il [StrongNameKeyGen](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygen-method.md) metodo crea una chiave a 1024 bit. Una volta recuperata la chiave, è necessario chiamare il [StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) metodo per rilasciare la memoria allocata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** MetaHost.h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameKeyGenEx](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamekeygenex-method.md)
- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
