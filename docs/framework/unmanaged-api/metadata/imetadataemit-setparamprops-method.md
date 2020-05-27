---
title: Metodo IMetaDataEmit::SetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
ms.openlocfilehash: b710f966f519e2702607b7e186fff5986110d391
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007819"
---
# <a name="imetadataemitsetparamprops-method"></a>Metodo IMetaDataEmit::SetParamProps
Imposta o modifica le funzionalità di un parametro del metodo definito da una chiamata precedente a [IMetaDataEmit::D efineparam](imetadataemit-defineparam-method.md).  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetParamProps (
    [in]  mdParamDef  pd,
    [in]  LPCWSTR     szName,
    [in]  DWORD       dwParamFlags,
    [in]  DWORD       dwCPlusTypeFlag,
    [in]  void const  *pValue,
    [in]  ULONG       cchValue
);  
```  
  
## <a name="parameters"></a>Parametri  
 `pd`  
 in Token per il parametro di destinazione.  
  
 `szName`  
 in Nome del parametro in formato Unicode.  
  
 `dwParamFlags`  
 in Flag per il parametro.  
  
 `dwCPlusTypeFlag`  
 in ELEMENT_TYPE_ * per il valore della costante.  
  
 `pValue`  
 in Valore costante per il parametro.  
  
 `cchValue`  
 in Dimensione in (Unicode) dei caratteri di `pValue` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MSCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
