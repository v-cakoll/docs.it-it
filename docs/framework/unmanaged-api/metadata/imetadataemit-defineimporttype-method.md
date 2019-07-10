---
title: Metodo IMetaDataEmit::DefineImportType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportType
helpviewer_keywords:
- DefineImportType method [.NET Framework metadata]
- IMetaDataEmit::DefineImportType method [.NET Framework metadata]
ms.assetid: 37fd27af-8062-4904-ace4-51bb78ec600a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ff0660ef2b30e32af540fe7bef5936ab6d0a359f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67777622"
---
# <a name="imetadataemitdefineimporttype-method"></a>Metodo IMetaDataEmit::DefineImportType
Crea un riferimento al tipo specificato che viene definito all'esterno dell'ambito corrente e definisce un token per tale riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineImportType (   
    [in]  IMetaDataAssemblyImport  *pAssemImport,   
    [in]  const void               *pbHashValue,   
    [in]  ULONG                    cbHashValue,    
    [in]  IMetaDataImport          *pImport,   
    [in]  mdTypeDef                tdImport,   
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,   
    [out] mdTypeRef                *ptr  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAssemImport`  
 [in] Un' [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia che rappresenta l'assembly dal quale viene importato il tipo di destinazione.  
  
 `pbHashValue`  
 [in] Matrice che contiene il valore hash per l'assembly specificato da `pAssemImport`.  
  
 `cbHashValue`  
 [in] Numero di byte nella matrice di `pbHashValue`.  
  
 `pImport`  
 [in] Un' [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia che rappresenta l'ambito dei metadati dal quale viene importato il tipo di destinazione.  
  
 `tdImport`  
 [in] Un `mdTypeDef` token che specifica il tipo di destinazione.  
  
 `pAssemEmit`  
 [in] Un' [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaccia che rappresenta l'assembly in cui viene importato il tipo di destinazione.  
  
 `ptr`  
 [out] Il `mdTypeRef` token definito nell'ambito corrente per il riferimento al tipo.  
  
## <a name="remarks"></a>Note  
 Prima di chiamare il [DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) metodo, è possibile usare il `DefineImportType` metodo per creare un riferimento di tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
