---
title: Metodo IMetaDataAssemblyImport::FindExportedTypeByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindExportedTypeByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindExportedTypeByName
helpviewer_keywords:
- FindExportedTypeByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindExportedTypeByName method [.NET Framework metadata]
ms.assetid: 46264b2c-574d-4dde-aafc-77187a104fdd
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 32a7b7b498cc4e52b8be3f43ae52293de380d9f7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "62044603"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>Metodo IMetaDataAssemblyImport::FindExportedTypeByName
Ottiene un puntatore a un tipo esportato, dato il nome e tipo di inclusione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,   
    [in]  mdToken           mdtExportedType,   
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szName`  
 [in] Il nome del tipo esportato.  
  
 `mdtExportedType`  
 [in] Il token di metadati per la classe contenitore del tipo esportato. Questo valore è `mdExportedTypeNil` se l'oggetto richiesto esportato tipo non è un tipo annidato.  
  
 `ptkExportedType`  
 [out] Un puntatore al `mdExportedType` token che rappresenta il tipo esportato.  
  
## <a name="remarks"></a>Note  
 Il `FindExportedTypeByName` metodo Usa le regole standard utilizzate da common language runtime per la risoluzione dei riferimenti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Come il runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
