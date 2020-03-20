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
ms.openlocfilehash: 15b58e01d4ce99f19f510c760819471b84380b45
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177763"
---
# <a name="imetadataassemblyimportgetexportedtypeprops-method"></a>Metodo IMetaDataAssemblyImport::GetExportedTypeProps
Ottiene il set di proprietà del tipo esportato con la firma dei metadati specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 [in] Token `mdExportedType` di metadati che rappresenta il tipo esportato.  
  
 `szName`  
 [fuori] Nome del tipo esportato.  
  
 `cchName`  
 [in] La dimensione, in caratteri `szName`larghi, di .  
  
 `pchName`  
 [fuori] Il numero di caratteri di larghezza effettivamente restituiti in`szName`  
  
 `ptkImplementation`  
 [fuori] Un `mdFile` `mdAssemblyRef`token `mdExportedType` , , o di metadati che contiene o consente l'accesso alle proprietà del tipo esportato.  
  
 `ptkTypeDef`  
 [fuori] Puntatore a `mdTypeDef` un token che rappresenta un tipo nel file.  
  
 `pdwExportedTypeFlags`  
 [fuori] Puntatore ai flag che descrivono i metadati applicati al tipo esportato. Il valore flags può essere uno o più [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
