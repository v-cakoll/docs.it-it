---
title: Metodo ICLRStrongName::StrongNameSignatureSize
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameSignatureSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameSignatureSize
helpviewer_keywords:
- ICLRStrongName::StrongNameSignatureSize method [.NET Framework hosting]
- StrongNameSignatureSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 76d4f93a-5e25-4399-abcc-a1389549481d
topic_type:
- apiref
ms.openlocfilehash: 7f6865c3d6dffa3b551d4e5e0636b1e386be8baa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134976"
---
# <a name="iclrstrongnamestrongnamesignaturesize-method"></a>Metodo ICLRStrongName::StrongNameSignatureSize
Restituisce le dimensioni della firma con nome sicuro. Questo metodo viene in genere usato dai compilatori per determinare la quantità di spazio da riservare nel file quando si crea un assembly con firma ritardata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT StrongNameSignatureSize (   
    [in]  BYTE   *pbPublicKeyBlob,  
    [in]  ULONG  cbPublicKeyBlob,   
    [in]  DWORD  *pcbSize  
);   
```  
  
## <a name="parameters"></a>Parametri  
 `pbPublicKeyBlob`  
 in Struttura di tipo [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) che contiene la parte pubblica della coppia di chiavi utilizzata per generare la firma con nome sicuro.  
  
 `cbPublicKeyBlob`  
 in Dimensione, in byte, del `pbPublicKeyBlob`.  
  
 `pcbSize`  
 in Numero di byte necessari per archiviare la firma con nome sicuro.  
  
## <a name="return-value"></a>Valore restituito  
 `S_OK` se il metodo è stato completato correttamente; in caso contrario, valore HRESULT che indica l'esito negativo (vedere [valori HRESULT comuni](https://go.microsoft.com/fwlink/?LinkId=213878) per un elenco).  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Metahost. h  
  
 **Libreria:** Incluso come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
