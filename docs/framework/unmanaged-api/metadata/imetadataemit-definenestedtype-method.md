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
ms.openlocfilehash: 2b24c2ca6907dfdb63ad934ec30557c246db174c
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004355"
---
# <a name="imetadataemitdefinenestedtype-method"></a>Metodo IMetaDataEmit::DefineNestedType
Crea la firma dei metadati di una definizione di tipo, restituisce un `mdTypeDef` token per quel tipo e specifica che il tipo definito è un membro del tipo a cui fa riferimento il `tdEncloser` parametro.  
  
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
 in Nome del tipo in Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` attributi. Si tratta di una maschera di maschera di `CorTypeAttr` valori.  
  
 `tkExtends`  
 in Token della classe di base. Si tratta di un `mdTypeDef` token o `mdTypeRef` .  
  
 `rtkImplements`[]  
 in Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.  
  
 `tdEncloser`  
 in Token del tipo di inclusione. L'ultimo elemento della matrice deve essere `mdTokenNil` .  
  
 `ptd`  
 out `mdTypeDef`Token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
