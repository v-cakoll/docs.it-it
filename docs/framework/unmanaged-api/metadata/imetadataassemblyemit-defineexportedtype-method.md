---
title: Metodo IMetaDataAssemblyEmit::DefineExportedType
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineExportedType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineExportedType
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineExportedType method [.NET Framework metadata]
- DefineExportedType method [.NET Framework metadata]
ms.assetid: fad01d7a-3178-4c8c-9f0a-4641e3701c9b
topic_type:
- apiref
ms.openlocfilehash: 44f97ef498eb8e64c55fc86b9f290b9e088293f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432064"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>Metodo IMetaDataAssemblyEmit::DefineExportedType
Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szName`  
 in Nome del tipo da esportare. Per la versione 1,1 della Common Language Runtime, il nome del tipo esportato deve corrispondere esattamente al nome specificato nel `TypeDef` per il tipo.  
  
 `tkImplementation`  
 in Token che specifica la posizione in cui viene implementato il tipo esportato. I valori validi e i significati associati sono:  
  
- `mdFile` il tipo viene implementato in un file diverso all'interno dell'assembly.  
  
- `mdAssemblyRef` il tipo viene implementato in un assembly diverso.  
  
- `mdExportedTYpe` il tipo è annidato all'interno di un altro tipo.  
  
- `mdFileNil` il tipo si trova nello stesso file del manifesto e non è un tipo annidato.  
  
 `tkTypeDef`  
 in Token per i metadati che specifica il tipo da esportare. Questo valore viene immesso nella tabella `TypeDef` nel file che implementa il tipo ed è pertinente solo se tale file si trova in questo assembly.  
  
 `dwExportedTypeFlags`  
 in Combinazione bit per bit di valori di enumerazione [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) che definiscono le impostazioni delle proprietà per il tipo esportato.  
  
 `pmdct`  
 out Puntatore al token di metadati restituito che indica il tipo esportato.  
  
## <a name="remarks"></a>Osservazioni  
 È necessario definire una struttura di metadati di `ExportedType` per ogni tipo esposto dall'assembly e che viene implementato in un modulo diverso da quello che contiene il manifesto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
