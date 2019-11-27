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
ms.openlocfilehash: 40f24a4ea628ce92a27ab1bfe97fc87a57dfa4f0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432553"
---
# <a name="imetadataemitdefinefield-method"></a>Metodo IMetaDataEmit::DefineField
Crea una definizione per un campo con la firma dei metadati specificata e ottiene un token per la definizione del campo.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Token `mdTypeDef` per la classe o l'interfaccia contenitore.  
  
 `szName`  
 in Nome del campo in Unicode.  
  
 `dwFieldFlags`  
 in Attributi del campo. Si tratta di una maschera di maschera dei valori `CorFieldAttr`.  
  
 `pvSigBlob`  
 in Firma del campo sotto forma di BLOB.  
  
 `cbSigBlob`  
 in Conteggio dei byte in `pvSigBlob`.  
  
 `dwCPlusTypeFlag`  
 in *\** `ELEMENT_TYPE_`per il valore della costante. Si tratta di un valore `CorElementType`. Se non si definisce un valore costante per il campo, utilizzare `ELEMENT_TYPE_END`.  
  
 `pValue`  
 in Valore costante per il campo.  
  
 `cchValue`  
 in Dimensioni in caratteri (Unicode) del `pValue`.  
  
 `pmd`  
 out Token `mdFieldDef` assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
