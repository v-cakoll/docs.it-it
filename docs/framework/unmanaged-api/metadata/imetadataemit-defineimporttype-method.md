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
ms.openlocfilehash: 6825a5198976cc7ab2c04ebd6e782418dcf4a8f7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177685"
---
# <a name="imetadataemitdefineimporttype-method"></a>Metodo IMetaDataEmit::DefineImportType
Crea un riferimento al tipo specificato definito all'esterno dell'ambito corrente e definisce un token per tale riferimento.  
  
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
 [in] Interfaccia [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) che rappresenta l'assembly da cui viene importato il tipo di destinazione.  
  
 `pbHashValue`  
 [in] Matrice che contiene l'hash per `pAssemImport`l'assembly specificato da .  
  
 `cbHashValue`  
 [in] Numero di byte nella matrice di `pbHashValue`.  
  
 `pImport`  
 [in] Interfaccia [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che rappresenta l'ambito dei metadati da cui viene importato il tipo di destinazione.  
  
 `tdImport`  
 [in] Token `mdTypeDef` che specifica il tipo di destinazione.  
  
 `pAssemEmit`  
 [in] Interfaccia [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) che rappresenta l'assembly in cui viene importato il tipo di destinazione.  
  
 `ptr`  
 [fuori] Token `mdTypeRef` definito nell'ambito corrente per il riferimento al tipo.  
  
## <a name="remarks"></a>Osservazioni  
 Prima di chiamare il [metodo IMetaDataEmit::DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md) , è possibile utilizzare il `DefineImportType` metodo per creare un riferimento al tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
