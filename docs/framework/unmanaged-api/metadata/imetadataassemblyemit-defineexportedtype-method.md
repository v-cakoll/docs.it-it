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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a2eb894a8bac702c30826d1e965c91cae9b259ee
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33448560"
---
# <a name="imetadataassemblyemitdefineexportedtype-method"></a>Metodo IMetaDataAssemblyEmit::DefineExportedType
Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineExportedType (  
    [in]  LPCWSTR             szName,  
    [in]  mdToken             tkImplementation,   
    [in]  mdTypeDef           tkTypeDef,  
    [in]  DWORD               dwExportedTypeFlags,  
    [out] mdExportedType      *pmdct  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `szName`  
 [in] Il nome del tipo da esportare. Per la versione 1.1 di common language runtime, il nome del tipo esportato deve corrispondere esattamente al nome fornito nel `TypeDef` per il tipo.  
  
 `tkImplementation`  
 [in] Un token che specifica in cui viene implementato il tipo esportato. I valori validi e il relativo significato è:  
  
-   `mdFile` Il tipo è implementato in un file diverso all'interno di questo assembly.  
  
-   `mdAssemblyRef` Il tipo viene implementato in un assembly diverso.  
  
-   `mdExportedTYpe` Il tipo è annidato all'interno di un altro tipo.  
  
-   `mdFileNil` Il tipo è nello stesso file del manifesto e non è un tipo annidato.  
  
 `tkTypeDef`  
 [in] Un token di metadati che specifica il tipo da esportare. Questo valore viene immesso nel `TypeDef` tabella nel file che implementa il tipo ed è rilevante solo se tale file è in questo assembly.  
  
 `dwExportedTypeFlags`  
 [in] Combinazione bit per bit di [CorTypeAttr](../../../../docs/framework/unmanaged-api/metadata/cortypeattr-enumeration.md) i valori di enumerazione che definiscono le impostazioni delle proprietà per il tipo esportato.  
  
 `pmdct`  
 [out] Puntatore al token di metadati restituito che indica il tipo esportato.  
  
## <a name="remarks"></a>Note  
 Un `ExportedType` struttura dei metadati deve essere definita per ogni tipo esposto da questo assembly e che viene implementato in un modulo diverso da quello che contiene il manifesto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
