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
ms.openlocfilehash: edfe5de9c9d7ef9607a2eea5146194bbd4393a92
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175993"
---
# <a name="imetadataassemblyimportfindexportedtypebyname-method"></a>Metodo IMetaDataAssemblyImport::FindExportedTypeByName
Ottiene un puntatore a un tipo esportato, dati il nome e il tipo di inclusione.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT FindExportedTypeByName (  
    [in]  LPCWSTR           szName,
    [in]  mdToken           mdtExportedType,
    [out] mdExportedType    *ptkExportedType  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szName`  
 [in] Nome del tipo esportato.  
  
 `mdtExportedType`  
 [in] Token di metadati per la classe contenitore del tipo esportato. Questo valore `mdExportedTypeNil` è se il tipo esportato richiesto non è un tipo annidato.  
  
 `ptkExportedType`  
 [fuori] Puntatore al `mdExportedType` token che rappresenta il tipo esportato.  
  
## <a name="remarks"></a>Osservazioni  
 Il `FindExportedTypeByName` metodo utilizza le regole standard utilizzate da Common Language Runtime per la risoluzione dei riferimenti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [Come il runtime individua gli assembly](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
