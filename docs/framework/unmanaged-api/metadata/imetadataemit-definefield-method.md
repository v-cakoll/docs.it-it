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
ms.openlocfilehash: 8ca5ab70f60de4d783800fb18612a8f04cb9cee1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177706"
---
# <a name="imetadataemitdefinefield-method"></a>Metodo IMetaDataEmit::DefineField
Crea una definizione per un campo con la firma dei metadati specificata e ottiene un token per tale definizione di campo.  
  
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
 [in] `mdTypeDef` Token per la classe o l'interfaccia che lo contiene.  
  
 `szName`  
 [in] Nome del campo in Unicode.  
  
 `dwFieldFlags`  
 [in] Attributi del campo. Si tratta di `CorFieldAttr` una maschera di bit di valori.  
  
 `pvSigBlob`  
 [in] Firma del campo come BLOB.  
  
 `cbSigBlob`  
 [in] Numero di byte `pvSigBlob`in .  
  
 `dwCPlusTypeFlag`  
 [in] Oggetto `ELEMENT_TYPE_` *\** per il valore costante. Questo è `CorElementType` un valore. Se non si definisce un `ELEMENT_TYPE_END`valore costante per il campo, utilizzare .  
  
 `pValue`  
 [in] Valore costante per il campo.  
  
 `cchValue`  
 [in] La dimensione in caratteri `pValue`(Unicode) di .  
  
 `pmd`  
 [fuori] Token `mdFieldDef` assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
