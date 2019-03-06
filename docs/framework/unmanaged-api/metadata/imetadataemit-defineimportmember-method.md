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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7ac44d29dd99e0205c515905f9846263033babf3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479298"
---
# <a name="imetadataemitdefineimportmember-method"></a>Metodo IMetaDataEmit::DefineImportMember
Crea un riferimento al membro specificato di un tipo o un modulo che viene definita all'esterno dell'ambito corrente e definisce un token per tale riferimento.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
 [in] Un' [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) interfaccia che rappresenta l'assembly dal quale viene importato il membro di destinazione.  
  
 `pbHashValue`  
 [in] Matrice che contiene il valore hash per l'assembly specificato da `pAssemImport`.  
  
 `cbHashValue`  
 [in] Numero di byte nella matrice di `pbHashValue`.  
  
 `pImport`  
 [in] Un' [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia che rappresenta l'ambito dei metadati dal quale viene importato il membro di destinazione.  
  
 `mbMember`  
 [in] Il token di metadati che specifica il membro di destinazione. Il token può essere un' `mdMethodDef` (per un metodo del membro), `mdProperty` (per una proprietà del membro), o `mdFieldDef` (per un campo membro) token.  
  
 `pAssemEmit`  
 [in] Un' [IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md) interfaccia che rappresenta l'assembly in cui viene importato il membro di destinazione.  
  
 `tkParent`  
 [in] Il `mdTypeRef` o `mdModuleRef` per il tipo o il modulo, rispettivamente, il proprietario del membro di destinazione.  
  
 `pmr`  
 [out] Il `mdMemberRef` token definito nell'ambito corrente per il riferimento al membro.  
  
## <a name="remarks"></a>Note  
 Il `DefineImportMember` metodo cerca il membro, specificato da `mbMember`, che viene definito in un altro ambito, specificato da `pImport`e recupera le relative proprietà. Questa informazione viene utilizzata per chiamare il [DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md) metodo nell'ambito corrente per creare il riferimento al membro.  
  
 In genere, prima di utilizzare il `DefineImportMember` metodo, è necessario creare, nell'ambito corrente, un riferimento al tipo o un riferimento di modulo per modulo, interfaccia o classe padre del membro di destinazione. Il token di metadati per questo riferimento viene quindi passato nel `tkParent` argomento. Non devi creare un riferimento all'elemento padre del membro di destinazione se che verrà risolto in un secondo momento dal compilatore o del linker. Per concludere:  
  
-   Se il membro di destinazione è un campo o un metodo, usare il [DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md) o il [DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md) metodo per creare un riferimento di tipo, nell'ambito corrente, per il classe padre o interfaccia padre del membro.  
  
-   Se il membro di destinazione è una funzione globale di variabili o globale (vale a dire, non un membro di una classe o interfaccia), usare il [DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md) metodo per creare un riferimento al modulo, nell'ambito corrente, per padre il membro modulo.  
  
-   Se l'elemento padre del membro di destinazione verrà risolto in un secondo momento dal compilatore o del linker, passare `mdTokenNil` in `tkParent`. L'unico scenario in cui si applica è quando una funzione globale o variabile globale viene importato da un file con estensione obj che infine verrà collegato al modulo corrente e i metadati verranno uniti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
