---
title: Metodo IMetaDataEmit::DefineNestedType
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 99250d98f9ffd90857128aa5d8a675a997926bf5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinenestedtype-method"></a>Metodo IMetaDataEmit::DefineNestedType
Crea la firma dei metadati di una definizione di tipo, restituisce un `mdTypeDef` token per il tipo e specifica che il tipo definito è un membro del tipo a cui fa riferimento il `tdEncloser` parametro.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineNestedType (   
    [in]  LPCWSTR     szTypeDef,  
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [in]  mdTypeDef   tdEncloser,   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szTypeDef`  
 [in] Il nome del tipo in formato Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` attributi. Si tratta di una maschera di bit di `CorTypeAttr` valori.  
  
 `tkExtends`  
 [in] Il token della classe di base. Questo è un `mdTypeDef` o `mdTypeRef` token.  
  
 `rtkImplements`[]  
 [in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.  
  
 `tdEncloser`  
 [in] Il token del tipo di inclusione. L'ultimo elemento della matrice deve essere `mdTokenNil`.  
  
 `ptd`  
 [out] Il `mdTypeDef` token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MSCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
