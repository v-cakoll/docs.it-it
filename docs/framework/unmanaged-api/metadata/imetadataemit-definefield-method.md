---
title: Metodo IMetaDataEmit::DefineField
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineField
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineField
helpviewer_keywords:
- IMetaDataEmit::DefineField method [.NET Framework metadata]
- DefineField method, IMetaDataEmit interface [.NET Framework metadata
ms.assetid: 6b5be4fc-2e86-499c-8b09-833160bca767
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8553665ba64a1c8e1cb6398d94cd1f772a566ed
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466661"
---
# <a name="imetadataemitdefinefield-method"></a>Metodo IMetaDataEmit::DefineField
Crea una definizione per un campo con la firma dei metadati specificati e ottiene un token per tale definizione di campo.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineField (   
    [in]  mdTypeDef   td,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwFieldFlags,   
    [in]  PCCOR_SIGNATURE pvSigBlob,   
    [in]  ULONG       cbSigBlob,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue,   
    [out] mdFieldDef  *pmd   
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 [in] Il `mdTypeDef` token per la classe o interfaccia che lo contiene.  
  
 `szName`  
 [in] Il nome del campo in formato Unicode.  
  
 `dwFieldFlags`  
 [in] Gli attributi di campo. Si tratta di una maschera di bit delle `CorFieldAttr` valori.  
  
 `pvSigBlob`  
 [in] La firma del campo come BLOB.  
  
 `cbSigBlob`  
 [in] Il numero di byte in `pvSigBlob`.  
  
 `dwCPlusTypeFlag`  
 [in] Il `ELEMENT_TYPE_` *\** per il valore costante. Si tratta di un `CorElementType` valore. Se non si definisce un valore costante per il campo, usare `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Il valore costante per il campo.  
  
 `cchValue`  
 [in] La dimensione in caratteri (Unicode) della `pValue`.  
  
 `pmd`  
 [out] Il `mdFieldDef` token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
