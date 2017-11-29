---
title: Metodo IMetaDataImport2::GetGenericParamProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af6ab8fd6e941f5219c1aad2946479dda0b64264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a>Metodo IMetaDataImport2::GetGenericParamProps
Ottiene i metadati associati al parametro generico rappresentato dal token specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `gp`  
 [in] Token che rappresenta il parametro generico per il quale restituire i metadati.  
  
 `pulParamSeq`  
 [out] La posizione ordinale del `Type` parametro nel metodo o nel costruttore padre.  
  
 `pdwParamFlags`  
 [out] Il valore di [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumerazione che descrive il `Type` per il parametro generico.  
  
 `ptOwner`  
 [out] Token TypeDef o MethodDef che rappresenta il proprietario del parametro.  
  
 `reserved`  
 [out] Riservato per l'estensibilità futura.  
  
 `wzName`  
 [out] Il nome del parametro generico.  
  
 `cchName`  
 [in] Le dimensioni del `wzName` buffer.  
  
 `pchName`  
 [out] Le dimensioni restituite del nome, in caratteri wide.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
