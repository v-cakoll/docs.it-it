---
title: Metodo IMetaDataEmit2::SetGenericParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.SetGenericParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::SetGenericParamProps
helpviewer_keywords:
- IMetaDataEmit2::SetGenericParamProps method [.NET Framework metadata]
- SetGenericParamProps method [.NET Framework metadata]
ms.assetid: cd93a48d-1fed-4706-bec6-a05dc3b64fbd
topic_type:
- apiref
ms.openlocfilehash: 8feba8e67f3a90dd48fd957065a9c166c204b87c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84492733"
---
# <a name="imetadataemit2setgenericparamprops-method"></a>Metodo IMetaDataEmit2::SetGenericParamProps
Imposta i valori delle proprietà per la definizione di parametro generico a cui fa riferimento il token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT SetGenericParamProps (  
    [in] mdGenericParam   gp,
    [in] DWORD            dwParamFlags,
    [in] LPCWSTR          szName,
    [in] DWORD            reserved,
    [in] mdToken          rtkConstraints[]  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `gp`  
 in Token per la definizione del parametro generico per il quale impostare i valori.  
  
 `dwParamFlags`  
 in Valore dell'enumerazione [CorGenericParamAttr](corgenericparamattr-enumeration.md) che descrive il tipo per il parametro generico.  
  
 `szName`  
 [in] Facoltativo. Nome del parametro per il quale impostare i valori.  
  
 `reserved`  
 in Riservato per l'estendibilità futura.  
  
 `rtkConstraints`  
 [in] Facoltativo. Matrice con terminazione zero di vincoli di tipo. I membri della matrice devono essere un `mdTypeDef` `mdTypeRef` token di metadati, o `mdTypeSpec` .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
- [Interfaccia IMetaDataEmit](imetadataemit-interface.md)
