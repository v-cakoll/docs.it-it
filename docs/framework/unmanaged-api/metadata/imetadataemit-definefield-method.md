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
ms.openlocfilehash: ccc4843864f375c167acdb12575c282dbe3a49e1
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84004816"
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
 in `mdTypeDef`Token per la classe o l'interfaccia contenitore.  
  
 `szName`  
 in Nome del campo in Unicode.  
  
 `dwFieldFlags`  
 in Attributi del campo. Si tratta di una maschera di maschera di `CorFieldAttr` valori.  
  
 `pvSigBlob`  
 in Firma del campo sotto forma di BLOB.  
  
 `cbSigBlob`  
 in Numero di byte in `pvSigBlob` .  
  
 `dwCPlusTypeFlag`  
 in Oggetto `ELEMENT_TYPE_` *\** per il valore della costante. Si tratta di un `CorElementType` valore. Se non si definisce un valore costante per il campo, usare `ELEMENT_TYPE_END` .  
  
 `pValue`  
 in Valore costante per il campo.  
  
 `cchValue`  
 in Dimensione in (Unicode) dei caratteri di `pValue` .  
  
 `pmd`  
 out `mdFieldDef`Token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
