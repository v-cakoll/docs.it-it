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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5bad338777db2097ed72ce327f42fde0f0db58e3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54693717"
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>Metodo IMetaDataAssemblyImport::GetManifestResourceProps
Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `mdmr`  
 [in] Un `mdManifestResource` token che rappresenta la risorsa per cui ottenere le proprietà.  
  
 `szName`  
 [out] Il nome della risorsa.  
  
 `cchName`  
 [in] Le dimensioni, in caratteri wide, di `szName`.  
  
 `pchName`  
 [out] Un puntatore al numero di caratteri wide effettivamente restituiti nella `szName`.  
  
 `ptkImplementation`  
 [out] Un puntatore a un `mdFile` token o un `mdAssemblyRef` token che rappresenta il file o l'assembly, rispettivamente, che contiene la risorsa.  
  
 `pdwOffset`  
 [out] Puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.  
  
 `pdwResourceFlags`  
 [out] Puntatore al flag che descrivono i metadati applicati a una risorsa. Il valore dei flag è una combinazione di uno o più [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
