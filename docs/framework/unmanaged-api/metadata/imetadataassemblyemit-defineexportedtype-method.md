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
ms.openlocfilehash: 388f227377ddf73fe1297e1c777bb1c0607c13d2
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177872"
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
 [in] Nome del tipo da esportare. Per la versione 1.1 di Common Language Runtime, il nome del tipo `TypeDef` esportato deve corrispondere esattamente al nome specificato nel per il tipo.  
  
 `tkImplementation`  
 [in] Token che specifica dove viene implementato il tipo esportato. I valori validi e i relativi significati associati sono:  
  
- `mdFile`Il tipo viene implementato in un file diverso all'interno di questo assembly.  
  
- `mdAssemblyRef`Il tipo viene implementato in un assembly diverso.  
  
- `mdExportedTYpe`Il tipo è annidato all'interno di un altro tipo.  
  
- `mdFileNil`Il tipo si trova nello stesso file del manifesto e non è un tipo annidato.  
  
 `tkTypeDef`  
 [in] Token per i metadati che specifica il tipo da esportare. Questo valore viene `TypeDef` immesso nella tabella del file che implementa il tipo ed è rilevante solo se tale file si trova in questo assembly.  
  
 `dwExportedTypeFlags`  
 [in] Combinazione bit per bit di [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) valori di enumerazione che definiscono le impostazioni delle proprietà per il tipo esportato.  
  
 `pmdct`  
 [fuori] Puntatore al token di metadati restituito che indica il tipo esportato.  
  
## <a name="remarks"></a>Osservazioni  
 Una `ExportedType` struttura di metadati deve essere definita per ogni tipo esposto da questo assembly e implementato in un modulo diverso da quello contenente il manifesto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
