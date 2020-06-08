---
title: Metodo IMetaDataImport::GetTypeDefProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetTypeDefProps
helpviewer_keywords:
- GetTypeDefProps method [.NET Framework metadata]
- IMetaDataImport::GetTypeDefProps method [.NET Framework metadata]
ms.assetid: 00061a25-ba05-47a7-b984-fd916b06b149
topic_type:
- apiref
ms.openlocfilehash: 6346b1e34e508e5c173bfd0119ac7451d7eef40e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490796"
---
# <a name="imetadataimportgettypedefprops-method"></a>Metodo IMetaDataImport::GetTypeDefProps
Restituisce le informazioni sui metadati per l'oggetto <xref:System.Type> rappresentato dal token TypeDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetTypeDefProps (  
   [in]  mdTypeDef   td,  
   [out] LPWSTR      szTypeDef,  
   [in]  ULONG       cchTypeDef,  
   [out] ULONG       *pchTypeDef,  
   [out] DWORD       *pdwTypeDefFlags,  
   [out] mdToken     *ptkExtends  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `td`  
 in Token TypeDef che rappresenta il tipo per cui restituire i metadati.  
  
 `szTypeDef`  
 out Buffer contenente il nome del tipo.  
  
 `cchTypeDef`  
 in Dimensioni in caratteri wide di `szTypeDef` .  
  
 `pchTypeDef`  
 out Numero di caratteri wide restituiti in `szTypeDef` .  
  
 `pdwTypeDefFlags`  
 out Puntatore a tutti i flag che modificano la definizione del tipo. Questo valore è una maschera di maschera dall'enumerazione [CorTypeAttr](cortypeattr-enumeration.md) .  
  
 `ptkExtends`  
 out Token di metadati TypeDef o TypeRef che rappresenta il tipo di base del tipo richiesto.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
