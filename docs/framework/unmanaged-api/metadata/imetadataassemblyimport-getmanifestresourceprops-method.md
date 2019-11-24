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
ms.openlocfilehash: c1792ed0f15f8cfb62567593c9694453650f0bb9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436326"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>Metodo IMetaDataAssemblyImport::GetManifestResourceProps
Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificata.  
  
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
 in Token `mdManifestResource` che rappresenta la risorsa per la quale ottenere le proprietà.  
  
 `szName`  
 out Nome della risorsa.  
  
 `cchName`  
 in Dimensione, in caratteri wide, di `szName`.  
  
 `pchName`  
 out Puntatore al numero di caratteri wide effettivamente restituiti in `szName`.  
  
 `ptkImplementation`  
 out Puntatore a un token di `mdFile` o a un token di `mdAssemblyRef` che rappresenta il file o l'assembly, rispettivamente, che contiene la risorsa.  
  
 `pdwOffset`  
 out Puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.  
  
 `pdwResourceFlags`  
 out Puntatore ai flag che descrivono i metadati applicati a una risorsa. Il valore dei flag è una combinazione di uno o più valori [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
