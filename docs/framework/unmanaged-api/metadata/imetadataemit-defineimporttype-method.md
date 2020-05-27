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
ms.openlocfilehash: edce5cb93b770fb5730e5a06633ffffacf332f7a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004693"
---
# <a name="imetadataemitdefineimporttype-method"></a>Metodo IMetaDataEmit::DefineImportType
Crea un riferimento al tipo specificato definito al di fuori dell'ambito corrente e definisce un token per il riferimento.  
  
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
 in Interfaccia [IMetaDataAssemblyImport](imetadataassemblyimport-interface.md) che rappresenta l'assembly da cui viene importato il tipo di destinazione.  
  
 `pbHashValue`  
 in Matrice contenente l'hash per l'assembly specificato da `pAssemImport` .  
  
 `cbHashValue`  
 [in] Numero di byte nella matrice di `pbHashValue`.  
  
 `pImport`  
 in Interfaccia [IMetaDataImport](imetadataimport-interface.md) che rappresenta l'ambito dei metadati da cui viene importato il tipo di destinazione.  
  
 `tdImport`  
 in `mdTypeDef`Token che specifica il tipo di destinazione.  
  
 `pAssemEmit`  
 in Interfaccia [IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md) che rappresenta l'assembly in cui viene importato il tipo di destinazione.  
  
 `ptr`  
 out `mdTypeRef`Token definito nell'ambito corrente per il riferimento al tipo.  
  
## <a name="remarks"></a>Commenti  
 Prima di chiamare il metodo [IMetaDataEmit::D efineimportmember](imetadataemit-defineimportmember-method.md) , è possibile usare il `DefineImportType` metodo per creare un riferimento a un tipo, nell'ambito corrente, per la classe padre o l'interfaccia padre del membro.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
