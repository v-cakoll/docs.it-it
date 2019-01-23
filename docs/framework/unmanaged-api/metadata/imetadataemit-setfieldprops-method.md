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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f05c6df415a92151783d805799da5bf7dfb6c7a4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556103"
---
# <a name="imetadataemitsetfieldprops-method"></a>Metodo IMetaDataEmit::SetFieldProps
Imposta o aggiorna il valore predefinito per il campo fa riferimento il token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT SetFieldProps (  
    [in]  mdFieldDef  fd,   
    [in]  DWORD       dwFieldFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `fd`  
 [in] Il token per il campo di destinazione.  
  
 `dwFieldFlags`  
 [in] Attributi di campo. Si tratta di una maschera di bit delle `CorFieldAttr` valori.  
  
 `dwCPlusTypeFlag`  
 [in] Il `ELEMENT_TYPE_` *\** per il valore costante. Si tratta di un `CorElementType` valore. Se non è definita una costante, impostare questo valore su `ELEMENT_TYPE_END`.  
  
 `pValue`  
 [in] Il valore costante per il campo.  
  
 `cchValue`  
 [in] Le dimensioni, in caratteri Unicode, di `pValue`.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
