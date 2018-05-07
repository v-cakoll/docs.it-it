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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5c250a577f2ccdbbfefb35225b880c0e4317db36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitdefineproperty-method"></a>Metodo IMetaDataEmit::DefineProperty
Crea una definizione di proprietà per il tipo specificato, con l'oggetto specificato `get` e `set` funzioni di accesso, metodo e ottiene un token per tale definizione.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `td`  
 [in] Il token per la classe o interfaccia in cui la proprietà è definita.  
  
 `szProperty`  
 [in] Il nome della proprietà.  
  
 `dwPropFlags`  
 [in] Flag della proprietà.  
  
 `pvSig`  
 [in] Firma della proprietà.  
  
 `cbSig`  
 [in] Il numero di byte in `pvSig`.  
  
 `dwCPlusTypeFlag`  
 [in] Il tipo di valore predefinito della proprietà.  
  
 `pValue`  
 [in] Il valore predefinito per la proprietà.  
  
 `cchValue`  
 [in] Il conteggio dei (Unicode) i caratteri `pValue`.  
  
 `mdSetter`  
 [in] Il metodo che imposta il valore della proprietà.  
  
 `mdGetter`  
 [in] Il metodo che ottiene il valore della proprietà.  
  
 `rmdOtherMethods[]`  
 [in] Matrice di altri metodi associato alla proprietà. Terminare la matrice con un `mdTokenNil`.  
  
 `pmdProp`  
 [out] Il `mdProperty` token assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
