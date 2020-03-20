---
title: Metodo IMetaDataEmit::DefineNestedType
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineNestedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineNestedType
helpviewer_keywords:
- IMetaDataEmit::DefineNestedType method [.NET Framework metadata]
- DefineNestedType method [.NET Framework metadata]
ms.assetid: 1e994de6-4628-459c-b967-b34be1e9fe4f
topic_type:
- apiref
ms.openlocfilehash: 3b8fd9876563bace52a6088747d1ca4ed26ea872
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175811"
---
# <a name="imetadataemitdefinenestedtype-method"></a>Metodo IMetaDataEmit::DefineNestedType
Crea la firma dei metadati `mdTypeDef` di una definizione di tipo, restituisce un token per tale `tdEncloser` tipo e specifica che il tipo definito è un membro del tipo a cui fa riferimento il parametro.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineNestedType (
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[],
    [in]  mdTypeDef   tdEncloser,
    [out] mdTypeDef   *ptd  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szTypeDef`  
 [in] Nome del tipo in Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` attributi. Si tratta di `CorTypeAttr` una maschera di bit di valori.  
  
 `tkExtends`  
 [in] Token della classe base. Si tratta `mdTypeDef` di `mdTypeRef` un o un token.  
  
 `rtkImplements`[]  
 [in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.  
  
 `tdEncloser`  
 [in] Token del tipo di inclusione. L'ultimo elemento della `mdTokenNil`matrice deve essere .  
  
 `ptd`  
 [fuori] Token `mdTypeDef` assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
