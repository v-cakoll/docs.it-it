---
title: Metodo IMetaDataEmit::DefineTypeDef
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineTypeDef
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineTypeDef
helpviewer_keywords:
- IMetaDataEmit::DefineTypeDef method [.NET Framework metadata]
- DefineTypeDef method [.NET Framework metadata]
ms.assetid: dd11c485-be95-4b97-9cd8-68679a4fb432
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 54691785e3b2619b5f4a2eecc510800b4b5cee07
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefinetypedef-method"></a>Metodo IMetaDataEmit::DefineTypeDef
Crea una definizione di tipo per un tipo common language runtime e ottiene un token di metadati per la definizione di tipo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineTypeDef (   
    [in]  LPCWSTR     szTypeDef,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[],   
    [out] mdTypeDef   *ptd  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szTypeDef`  
 [in] Il nome del tipo in formato Unicode.  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` attributi. Si tratta di una maschera di bit di `CoreTypeAttr` valori.  
  
 `tkExtends`  
 [in] Il token della classe di base. Deve essere un `mdTypeDef` o `mdTypeRef` token.  
  
 `rtkImplements`  
 [in] Matrice di token che specificano le interfacce implementate da questa classe o interfaccia.  
  
 `ptd`  
 [out] Il `mdTypeDef` token assegnato.  
  
## <a name="remarks"></a>Note  
 Un flag nel `dwTypeDefFlags` specifica se il tipo creato è un tipo di sistema tipo comuni (classe o interfaccia) o un tipo di valore di sistema tipo comune.  
  
 A seconda dei parametri forniti, questo metodo, come effetto collaterale, potrebbe anche creare un `mdInterfaceImpl` record per ogni interfaccia implementata da questo tipo o ereditata. Tuttavia, questo metodo non restituisce uno di questi `mdInterfaceImpl` token. Se un client desidera aggiungere o modificare un secondo momento un `mdInterfaceImpl` token, è necessario utilizzare il `IMetaDataImport` interfaccia per enumerarli. Se si desidera utilizzare la semantica di COM del `[default]` interfaccia, è necessario fornire l'interfaccia predefinita come primo elemento in `rtkImplements`; un attributo personalizzato impostato nella classe indicherà che la classe dispone di un'interfaccia predefinita (che viene sempre considerato il prima di tutto `mdInterfaceImpl` token dichiarato per la classe).  
  
 Ogni elemento del `rtkImplements` matrice contiene un `mdTypeDef` o `mdTypeRef` token. Deve essere l'ultimo elemento nella matrice `mdTokenNil`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
