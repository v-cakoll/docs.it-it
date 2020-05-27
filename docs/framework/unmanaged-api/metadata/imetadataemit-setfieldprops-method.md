---
title: Metodo IMetaDataEmit::SetFieldProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetFieldProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetFieldProps
helpviewer_keywords:
- IMetaDataEmit::SetFieldProps method [.NET Framework metadata]
- SetFieldProps method [.NET Framework metadata]
ms.assetid: 47132dda-fa92-4bd1-ae4b-24cd9a60665a
topic_type:
- apiref
ms.openlocfilehash: 220556ec130c7bff7c413405820c4fee0582b051
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008014"
---
# <a name="imetadataemitsetfieldprops-method"></a>Metodo IMetaDataEmit::SetFieldProps
Imposta o aggiorna il valore predefinito per il campo a cui fa riferimento il token di campo specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,
    [in]  DWORD       dwFieldFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a>Parametri  
 `fd`  
 in Token per il campo di destinazione.  
  
 `dwFieldFlags`  
 in Attributi di campo. Si tratta di una maschera di maschera di `CorFieldAttr` valori.  
  
 `dwCPlusTypeFlag`  
 in Oggetto `ELEMENT_TYPE_` *\** per il valore della costante. Si tratta di un `CorElementType` valore. Se una costante non viene definita, impostare questo valore su `ELEMENT_TYPE_END` .  
  
 `pValue`  
 in Valore costante per il campo.  
  
 `cchValue`  
 in Dimensione, in caratteri Unicode, di `pValue` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
