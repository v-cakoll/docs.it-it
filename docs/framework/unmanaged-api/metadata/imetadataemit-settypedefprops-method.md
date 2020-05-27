---
title: Metodo IMetaDataEmit::SetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: b05527f118de059c674ea659b1a22b7895126cf4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007767"
---
# <a name="imetadataemitsettypedefprops-method"></a>Metodo IMetaDataEmit::SetTypeDefProps
Imposta le funzionalità di un tipo definito da una chiamata precedente a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 in `mdTypeDef`Token ottenuto dalla chiamata originale a [IMetaDataEmit::D efinetypedef](imetadataemit-definetypedef-method.md).  
  
 `dwTypeDefFlags`  
 [in] `TypeDef` attributi. Si tratta di una maschera di maschera di `CorTypeAttr` valori.  
  
 `tkExtends`  
 in Oggetto `mdToken` della classe di base. Ottenuta da una chiamata precedente a [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md), o `null` .  
  
 `rtkImplements[]`  
 in Matrice di token per le interfacce implementate da questo tipo. Questi `mdTypeRef` token vengono ottenuti utilizzando [IMetaDataEmit::D efineimporttype](imetadataemit-defineimporttype-method.md). L'ultimo elemento della matrice deve essere `mdTokenNil` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
