---
title: Metodo IMetaDataAssemblyImport::GetExportedTypeProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetExportedTypeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetExportedTypeProps
helpviewer_keywords:
- GetExportedTypeProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetExportedTypeProps method [.NET Framework metadata]
ms.assetid: 25ca7623-5a55-4f09-b44a-36b03d142278
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 91b1e4469f07954dc433769911c78d72bb3c36cb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096150"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>Metodo IMetaDataAssemblyImport::GetExportedTypeProps
Ottiene il set di proprietà del tipo esportato con la firma dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetExportedTypeProps (  
    [in]  mdExportedType    mdct,   
    [out] LPWSTR            szName,   
    [in]  ULONG             cchName,   
    [out] ULONG             *pchName,   
    [out] mdToken           *ptkImplementation,   
    [out] mdTypeDef         *ptkTypeDef,   
    [out] DWORD             *pdwExportedTypeFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mdct`  
 [in] Un `mdExportedType` token di metadati che rappresenta il tipo esportato.  
  
 `szName`  
 [out] Il nome del tipo esportato.  
  
 `cchName`  
 [in] Le dimensioni, in caratteri "wide", di `szName`.  
  
 `pchName`  
 [out] Il numero di caratteri "wide" è effettivamente restituiti nella `szName`  
  
 `ptkImplementation`  
 [out] Un' `mdFile`, `mdAssemblyRef`, o `mdExportedType` token di metadati che contiene o consente l'accesso alle proprietà del tipo esportato.  
  
 `ptkTypeDef`  
 [out] Un puntatore a un `mdTypeDef` token che rappresenta un tipo nel file.  
  
 `pdwExportedTypeFlags`  
 [out] Puntatore ai flag che descrivono i metadati applicati al tipo esportato. Il valore del flag può essere uno o più [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
