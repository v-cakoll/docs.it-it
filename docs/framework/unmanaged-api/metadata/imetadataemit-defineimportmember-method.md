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
ms.openlocfilehash: 2facc63023a20dd6aaac64d7d036324c31658bc8
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501313"
---
# <a name="imetadataemitdefineimportmember-method"></a>Metodo IMetaDataEmit::DefineImportMember
Crea un riferimento al membro specificato di un tipo o di un modulo definito al di fuori dell'ambito corrente e definisce un token per il riferimento.  
  
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
 in Interfaccia [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) che rappresenta l'assembly da cui viene importato il membro di destinazione.  
  
 `pbHashValue`  
 in Matrice contenente l'hash per l'assembly specificato da `pAssemImport` .  
  
 `cbHashValue`  
 [in] Numero di byte nella matrice di `pbHashValue`.  
  
 `pImport`  
 in Interfaccia [IMetaDataImport](imetadataimport-interface.md) che rappresenta l'ambito dei metadati da cui viene importato il membro di destinazione.  
  
 `mbMember`  
 in Token di metadati che specifica il membro di destinazione. Il token può essere un `mdMethodDef` (per un metodo membro), `mdProperty` (per una proprietà del membro) o `mdFieldDef` (per un campo del membro).  
  
 `pAssemEmit`  
 in Interfaccia [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) che rappresenta l'assembly in cui viene importato il membro di destinazione.  
  
 `tkParent`  
 in `mdTypeRef`Token o `mdModuleRef` per il tipo o il modulo, rispettivamente, proprietario del membro di destinazione.  
  
 `pmr`  
 out `mdMemberRef`Token definito nell'ambito corrente per il riferimento al membro.  
  
## <a name="remarks"></a>Osservazioni  
 Il `DefineImportMember` metodo cerca il membro, specificato da `mbMember` , che è definito in un altro ambito, specificato da `pImport` , e ne recupera le proprietà. Usa queste informazioni per chiamare il metodo [IMetaDataEmit::D efinememberref](imetadataemit-definememberref-method.md) nell'ambito corrente per creare il riferimento al membro.  
  
 In genere, prima di usare il `DefineImportMember` metodo, è necessario creare, nell'ambito corrente, un riferimento al tipo o un riferimento al modulo per la classe, l'interfaccia o il modulo padre del membro di destinazione. Il token di metadati per il riferimento viene quindi passato nell' `tkParent` argomento. Non è necessario creare un riferimento all'elemento padre del membro di destinazione se verrà risolto in un secondo momento dal compilatore o dal linker. Per concludere:  
  
- Se il membro di destinazione è un campo o un metodo, usare il metodo [IMetaDataEmit::D efinetyperefbyname](imetadataemit-definetyperefbyname-method.md) o [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md) per creare un riferimento al tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.  
  
- Se il membro di destinazione è una variabile globale o una funzione globale (ovvero non è un membro di una classe o di un'interfaccia), usare il metodo [IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md) per creare un riferimento al modulo nell'ambito corrente per il modulo padre del membro.  
  
- Se il padre del membro di destinazione verrà risolto in un secondo momento dal compilatore o dal linker, passare `mdTokenNil` `tkParent` . L'unico scenario in cui si applica si verifica quando una funzione globale o una variabile globale viene importata da un file con estensione obj che verrà infine collegato al modulo corrente e i metadati vengono uniti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
