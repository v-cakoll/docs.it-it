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
ms.openlocfilehash: eb3ecbf39376e7126b5ec93a26badcbf5076d1db
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175785"
---
# <a name="imetadataemitdefineproperty-method"></a>Metodo IMetaDataEmit::DefineProperty
Crea una definizione di proprietà per `get` `set` il tipo specificato, con le funzioni di accesso al metodo e e specificate e ottiene un token per tale definizione di proprietà.  
  
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
 [in] Token per la classe o l'interfaccia in cui viene definita la proprietà.  
  
 `szProperty`  
 [in] Nome della proprietà.  
  
 `dwPropFlags`  
 [in] Flag della proprietà.  
  
 `pvSig`  
 [in] Firma della proprietà.  
  
 `cbSig`  
 [in] Numero di byte `pvSig`in .  
  
 `dwCPlusTypeFlag`  
 [in] Tipo del valore predefinito della proprietà.  
  
 `pValue`  
 [in] Valore predefinito per la proprietà.  
  
 `cchValue`  
 [in] Numero di caratteri (Unicode) in `pValue`.  
  
 `mdSetter`  
 [in] Metodo che imposta il valore della proprietà.  
  
 `mdGetter`  
 [in] Metodo che ottiene il valore della proprietà.  
  
 `rmdOtherMethods[]`  
 [in] Matrice di altri metodi associati alla proprietà. Terminare la matrice `mdTokenNil`con un oggetto .  
  
 `pmdProp`  
 [fuori] Token `mdProperty` assegnato.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
