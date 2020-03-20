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
ms.openlocfilehash: b921118f7c43edef3c07cbb34cbbd9119d36ce51
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177559"
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
 [in] Token per il campo di destinazione.  
  
 `dwFieldFlags`  
 [in] Attributi del campo. Si tratta di `CorFieldAttr` una maschera di bit di valori.  
  
 `dwCPlusTypeFlag`  
 [in] Oggetto `ELEMENT_TYPE_` *\** per il valore costante. Questo è `CorElementType` un valore. Se non viene definita una costante, `ELEMENT_TYPE_END`impostare questo valore su .  
  
 `pValue`  
 [in] Valore costante per il campo.  
  
 `cchValue`  
 [in] La dimensione, in caratteri `pValue`Unicode, di .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MSCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
