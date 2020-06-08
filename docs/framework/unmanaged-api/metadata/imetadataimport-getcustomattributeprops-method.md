---
title: Metodo IMetaDataImport::GetCustomAttributeProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetCustomAttributeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetCustomAttributeProps
helpviewer_keywords:
- GetCustomAttributeProps method [.NET Framework metadata]
- IMetaDataImport::GetCustomAttributeProps method [.NET Framework metadata]
ms.assetid: 6eefb243-a281-41c1-bcdc-7e17513bc446
topic_type:
- apiref
ms.openlocfilehash: 320cfae93f8aae94f9315e8e20ed6cf7f9cced7c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491316"
---
# <a name="imetadataimportgetcustomattributeprops-method"></a>Metodo IMetaDataImport::GetCustomAttributeProps
Ottiene il valore dell'attributo personalizzato, dato il relativo token di metadati.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetCustomAttributeProps (  
   [in]            mdCustomAttribute   cv,  
   [out, optional] mdToken             *ptkObj,  
   [out, optional] mdToken             *ptkType,  
   [out, optional] void const          **ppBlob,  
   [out, optional] ULONG               *pcbSize  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `cv`  
 [in] Token di metadati che rappresenta l'attributo personalizzato da recuperare.  
  
 `ptkObj`  
 [out, facoltativo] Token di metadati che rappresenta l'oggetto che viene modificato dall'attributo personalizzato. Questo valore può essere un tipo qualsiasi di token di metadati, eccetto `mdCustomAttribute`.  
  
 `ptkType`  
 [out, facoltativo] Token di metadati `mdMethodDef` o `mdMemberRef` che rappresenta la classe <xref:System.Type> dell'attributo personalizzato restituito.  
  
 `ppBlob`  
 [out, facoltativo] Puntatore a una matrice di dati che è il valore dell'attributo personalizzato.  
  
 `pcbSize`  
 [out, facoltativo] Dimensione in byte dei dati restituiti in *`ppBlob`.  
  
## <a name="remarks"></a>Osservazioni  
 Un attributo personalizzato viene archiviato come matrice di dati, il formato riconosciuto dal modulo di gestione dei metadati.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
