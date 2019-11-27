---
title: Metodo IMetaDataEmit::SetEventProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetEventProps
helpviewer_keywords:
- IMetaDataEmit::SetEventProps method [.NET Framework metadata]
- SetEventProps method [.NET Framework metadata]
ms.assetid: 3b039e50-63ec-4730-99ff-2327408de477
topic_type:
- apiref
ms.openlocfilehash: 506e13ad956a01b16e36d8c71737fe0efce4c01b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450324"
---
# <a name="imetadataemitseteventprops-method"></a>Metodo IMetaDataEmit::SetEventProps
Imposta o aggiorna la funzionalità specificata di un evento definito da una chiamata precedente a [IMetaDataEmit::D efineevent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetEventProps (  
    [in]  mdEvent     ev,   
    [in]  DWORD       dwEventFlags,   
    [in]  mdToken     tkEventType,   
    [in]  mdMethodDef mdAddOn,   
    [in]  mdMethodDef mdRemoveOn,   
    [in]  mdMethodDef mdFire,   
    [in]  mdMethodDef rmdOtherMethods[]   
);  
```  
  
## <a name="parameters"></a>Parametri  
 `ev`  
 in Token dell'evento.  
  
 `dwEventFlags`  
 in Flag evento. Si tratta di una maschera di maschera dei valori `CorEventAttr`.  
  
 `tkEventType`  
 in Token per la classe di evento. Si tratta di un token `mdTypeDef` o `mdTypeRef`.  
  
 `mdAddOn`  
 in Metodo utilizzato per sottoscrivere l'evento o null.  
  
 `mdRemoveOn`  
 in Metodo utilizzato per annullare la sottoscrizione dell'evento o null.  
  
 `mdFire`  
 in Metodo usato (da una classe derivata) per generare l'evento.  
  
 `rmdOtherMethods[]`  
 in Matrice di token per altri metodi associati all'evento. L'ultimo elemento della matrice deve essere `mdMethodDefNil`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
