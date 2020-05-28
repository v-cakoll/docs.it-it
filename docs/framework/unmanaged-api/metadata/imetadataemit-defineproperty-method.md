---
title: Metodo IMetaDataEmit::DefineProperty
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineProperty
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineProperty
helpviewer_keywords:
- IMetaDataEmit::DefineProperty method [.NET Framework metadata]
- DefineProperty method [.NET Framework metadata]
ms.assetid: 5c4c1dc2-d40d-4173-bbe6-7058fb21c98f
topic_type:
- apiref
ms.openlocfilehash: 479cb25ad8e1c263d3539a4203ac5bea781eb931
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009379"
---
# <a name="imetadataemitdefineproperty-method"></a>Metodo IMetaDataEmit::DefineProperty
Crea una definizione di proprietà per il tipo specificato, con le `get` funzioni di accesso ai metodi e specificate `set` , e ottiene un token per la definizione della proprietà.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineProperty (
    [in]  mdTypeDef          td,
    [in]  LPCWSTR            szProperty,
    [in]  DWORD              dwPropFlags,
    [in]  PCCOR_SIGNATURE    pvSig,
    [in]  ULONG              cbSig,
    [in]  DWORD              dwCPlusTypeFlag,
    [in]  void const         *pValue,
    [in]  ULONG              cchValue,
    [in]  mdMethodDef        mdSetter,
    [in]  mdMethodDef        mdGetter,
    [in]  mdMethodDef        rmdOtherMethods[],
    [out] mdProperty         *pmdProp
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 in Token per la classe o l'interfaccia in cui viene definita la proprietà.  
  
 `szProperty`  
 [in] Nome della proprietà.  
  
 `dwPropFlags`  
 in Flag della proprietà.  
  
 `pvSig`  
 in Firma della proprietà.  
  
 `cbSig`  
 in Numero di byte in `pvSig` .  
  
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
 in Matrice di altri metodi associati alla proprietà. Terminare la matrice con un oggetto `mdTokenNil` .  
  
 `pmdProp`  
 out `mdProperty`Token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
