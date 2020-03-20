---
title: Metodo IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
ms.openlocfilehash: d87d0d46ede65cf44c84edba92fe246174088a4e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177652"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>Metodo IMetaDataAssemblyImport::GetManifestResourceProps
Ottiene il set di proprietà della risorsa di manifesto con la firma dei metadati specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] mdToken              *ptkImplementation,
    [out] DWORD                *pdwOffset,
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mdmr`  
 [in] Token `mdManifestResource` che rappresenta la risorsa per la quale ottenere le proprietà.  
  
 `szName`  
 [fuori] Nome della risorsa.  
  
 `cchName`  
 [in] La dimensione, in caratteri `szName`ampi, di .  
  
 `pchName`  
 [fuori] Puntatore al numero di caratteri wide `szName`effettivamente restituiti in .  
  
 `ptkImplementation`  
 [fuori] Puntatore a `mdFile` un `mdAssemblyRef` token o a un token che rappresenta rispettivamente il file o l'assembly che contiene la risorsa.  
  
 `pdwOffset`  
 [fuori] Puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.  
  
 `pdwResourceFlags`  
 [fuori] Puntatore a flag che descrivono i metadati applicati a una risorsa. Il valore flags è una combinazione di uno o più [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
