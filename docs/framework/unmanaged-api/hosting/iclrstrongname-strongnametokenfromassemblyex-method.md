---
title: Metodo ICLRStrongName::StrongNameTokenFromAssemblyEx
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
ms.openlocfilehash: e504aa067d51ec62d42f019c3a9e40538e374ea1
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762617"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a>Metodo ICLRStrongName::StrongNameTokenFromAssemblyEx
Crea un token con nome sicuro dal file di assembly specificato e restituisce la chiave pubblica rappresentata dal token.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameTokenFromAssemblyEx (  
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
 `S_OK`Se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](/windows/win32/seccrypto/common-hresult-values) per un elenco).  
  
## <a name="remarks"></a>Osservazioni  
 Un token di nome sicuro è il formato abbreviato di una chiave pubblica. Il token è un hash a 64 bit creato dalla chiave pubblica usata per firmare l'assembly. Il token fa parte del nome sicuro dell'assembly e può essere letto dai metadati dell'assembly.  
  
 Dopo che la chiave è stata recuperata e il token è stato creato, è necessario chiamare il metodo [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) per rilasciare la memoria allocata.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Metodo StrongNameTokenFromAssembly](iclrstrongname-strongnametokenfromassembly-method.md)
- [Interfaccia ICLRStrongName](iclrstrongname-interface.md)
