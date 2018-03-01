---
title: Metodo IMetaDataAssemblyImport::GetFileProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataAssemblyImport.GetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetFileProps
helpviewer_keywords:
- GetFileProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetFileProps method [.NET Framework metadata]
ms.assetid: c5e6216f-ae3d-4697-9688-66b69c1251ec
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 55984c4adaf291e3b962514cdc3bea964d1c91bb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataassemblyimportgetfileprops-method"></a>Metodo IMetaDataAssemblyImport::GetFileProps
Ottiene le proprietà del file con la firma dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetFileProps (  
    [in]  mdFile      mdf,   
    [out] LPWSTR      szName,   
    [in]  ULONG       cchName,   
    [out] ULONG       *pchName,   
    [out] const void  **ppbHashValue,   
    [out] ULONG       *pcbHashValue,   
    [out] DWORD       *pdwFileFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mdf`  
 [in] Il `mdFile` token di metadati che rappresenta il file per cui ottenere le proprietà.  
  
 `szName`  
 [out] Il nome semplice del file.  
  
 `cchName`  
 [in] La dimensione in caratteri wide, di `szName`.  
  
 `pchName`  
 [out] Numero di caratteri "wide" effettivamente restituiti nella `szName`.  
  
 `ppbHashValue`  
 [out] Puntatore al valore hash. Si tratta dell'hash, usando l'algoritmo SHA-1, del file.  
  
 `pcbHashValue`  
 [out] Il numero di caratteri "wide" nel valore hash restituito.  
  
 `pdwFileFlags`  
 [out] Un puntatore per i flag che descrivono i metadati applicati a un file. Il valore del flag è una combinazione di uno o più [CorFileFlags](../../../../docs/framework/unmanaged-api/metadata/corfileflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
