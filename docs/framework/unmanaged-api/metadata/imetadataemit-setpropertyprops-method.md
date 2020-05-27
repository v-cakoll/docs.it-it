---
title: Metodo IMetaDataEmit::SetPropertyProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPropertyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPropertyProps
helpviewer_keywords:
- SetPropertyProps method [.NET Framework metadata]
- IMetaDataEmit::SetPropertyProps method [.NET Framework metadata]
ms.assetid: e2501fc8-b2bc-4dcc-9205-e3acd5a53ffe
topic_type:
- apiref
ms.openlocfilehash: b5af877c26c20bf64a27618bf24a7bce5b410419
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007780"
---
# <a name="imetadataemitsetpropertyprops-method"></a>Metodo IMetaDataEmit::SetPropertyProps
Imposta le funzionalità archiviate nei metadati per una proprietà definita da una chiamata precedente al [Metodo DefineProperty](imetadataemit-defineproperty-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetPropertyProps (
    [in]  mdProperty      pr,
    [in]  DWORD           dwPropFlags,
    [in]  DWORD           dwCPlusTypeFlag,
    [in]  void const      *pValue,
    [in]  ULONG           cchValue,
    [in]  mdMethodDef     mdSetter,
    [in]  mdMethodDef     mdGetter,
    [in]  mdMethodDef     rmdOtherMethods[]
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pr`  
 in Token per la proprietà da modificare  
  
 `dwPropFlags`  
 in Flag della proprietà.  
  
 `dwCPlusTypeFlag`  
 in Tipo del valore predefinito della proprietà.  
  
 `pValue`  
 in Valore predefinito per la proprietà.  
  
 `cchValue`  
 in Numero di caratteri (Unicode) in `pValue` .  
  
 `mdSetter`  
 in Metodo che imposta il valore della proprietà.  
  
 `mdGetter`  
 in Metodo che ottiene il valore della proprietà.  
  
 `rmdOtherMethods[]`  
 in Matrice di altri metodi associati alla proprietà. Termina la matrice con un `mdTokenNil` token.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
