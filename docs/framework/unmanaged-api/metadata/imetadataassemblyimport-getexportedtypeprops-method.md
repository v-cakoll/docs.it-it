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
ms.openlocfilehash: 944941c2356cae93ecc85f1714b4b29aefcb50ad
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008404"
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
 in `mdExportedType`Token di metadati che rappresenta il tipo esportato.  
  
 `szName`  
 out Nome del tipo esportato.  
  
 `cchName`  
 in Dimensione, in caratteri wide, di `szName` .  
  
 `pchName`  
 out Numero di caratteri wide effettivamente restituiti in`szName`  
  
 `ptkImplementation`  
 out `mdFile` `mdAssemblyRef` `mdExportedType` Token di metadati, o che contiene o consente l'accesso alle proprietà del tipo esportato.  
  
 `ptkTypeDef`  
 out Puntatore a un `mdTypeDef` token che rappresenta un tipo nel file.  
  
 `pdwExportedTypeFlags`  
 out Puntatore ai flag che descrivono i metadati applicati al tipo esportato. Il valore dei flag può essere uno o più valori [CorTypeAttr](cortypeattr-enumeration.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
