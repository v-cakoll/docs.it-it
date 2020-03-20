---
title: Metodo IMetaDataEmit::DefineImportMember
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineImportMember
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineImportMember
helpviewer_keywords:
- DefineImportMember method [.NET Framework metadata]
- IMetaDataEmit::DefineImportMember method [.NET Framework metadata]
ms.assetid: c7dd94c6-335b-46ff-9dfe-505056db5673
topic_type:
- apiref
ms.openlocfilehash: a7449ffc8a8ccf2db62ab3cff2f9cfaffd0c72a9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175863"
---
# <a name="imetadataemitdefineimportmember-method"></a>Metodo IMetaDataEmit::DefineImportMember
Crea un riferimento al membro specificato di un tipo o modulo definito all'esterno dell'ambito corrente e definisce un token per tale riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineImportMember (
    [in]  IMetaDataAssemblyImport  *pAssemImport,
    [in]  const void               *pbHashValue,
    [in]  ULONG                    cbHashValue,  
    [in]  IMetaDataImport          *pImport,
    [in]  mdToken                  mbMember,
    [in]  IMetaDataAssemblyEmit    *pAssemEmit,
    [in]  mdToken                  tkParent,
    [out] mdMemberRef              *pmr
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pAssemImport`  
 [in] Interfaccia [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) che rappresenta l'assembly da cui viene importato il membro di destinazione.  
  
 `pbHashValue`  
 [in] Matrice che contiene l'hash per `pAssemImport`l'assembly specificato da .  
  
 `cbHashValue`  
 [in] Numero di byte nella matrice di `pbHashValue`.  
  
 `pImport`  
 [in] Interfaccia [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) che rappresenta l'ambito dei metadati da cui viene importato il membro di destinazione.  
  
 `mbMember`  
 [in] Token di metadati che specifica il membro di destinazione. Il token può `mdMethodDef` essere un token `mdProperty` (per un metodo `mdFieldDef` membro), (per una proprietà del membro) o (per un campo membro).  
  
 `pAssemEmit`  
 [in] Interfaccia [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) che rappresenta l'assembly in cui viene importato il membro di destinazione.  
  
 `tkParent`  
 [in] Il `mdTypeRef` `mdModuleRef` token o per il tipo o modulo, rispettivamente, che possiede il membro di destinazione.  
  
 `pmr`  
 [fuori] Token `mdMemberRef` definito nell'ambito corrente per il riferimento al membro.  
  
## <a name="remarks"></a>Osservazioni  
 Il `DefineImportMember` metodo cerca il membro `mbMember`, specificato da , definito `pImport`in un altro ambito, specificato da , e ne recupera le proprietà. Utilizza queste informazioni per chiamare il metodo [IMetaDataEmit::DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) nell'ambito corrente per creare il riferimento al membro.  
  
 In genere, prima `DefineImportMember` di utilizzare il metodo, è necessario creare, nell'ambito corrente, un riferimento al tipo o un riferimento al modulo per la classe padre, l'interfaccia o il modulo del membro di destinazione. Il token di metadati per `tkParent` questo riferimento viene quindi passato nell'argomento. Non è necessario creare un riferimento all'elemento padre del membro di destinazione se verrà risolto in un secondo momento dal compilatore o dal linker. Per riepilogare:  
  
- Se il membro di destinazione è un campo o un metodo, utilizzare il [Metodo IMetaDataEmit::DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) per creare un riferimento al tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.  
  
- Se il membro di destinazione è una variabile globale o una funzione globale, ovvero non è un membro di una classe o di un'interfaccia, utilizzare il metodo [IMetaDataEmit::DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) per creare un riferimento al modulo, nell'ambito corrente, per il modulo padre del membro.  
  
- Se l'elemento padre del membro di destinazione verrà risolto `mdTokenNil` `tkParent`in un secondo momento dal compilatore o dal linker, passare . L'unico scenario in cui questo si applica è quando una funzione globale o una variabile globale viene importata da un file obj che verrà infine collegato nel modulo corrente e i metadati uniti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
