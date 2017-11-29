---
title: Metodo IMetaDataImport::GetParamProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3f36282df52b316bfa32c50c3fa9f55f829aa04e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgetparamprops-method"></a>Metodo IMetaDataImport::GetParamProps
Ottiene i valori di metadati relativi al parametro a cui fa riferimento il token ParamDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `tk`  
 [in] Token ParamDef che rappresenta il parametro per restituire i metadati.  
  
 `pmd`  
 [out] Un puntatore a un token MethodDef che rappresenta il metodo che accetta il parametro.  
  
 `pulSequence`  
 [out] La posizione ordinale del parametro nell'elenco di argomenti di metodo.  
  
 `szName`  
 [out] Un buffer contenente il nome del parametro.  
  
 `cchName`  
 [in] La dimensione in caratteri wide della richiesta `szName`.  
  
 `pchName`  
 [out] Dimensione restituita in caratteri "wide" di `szName`.  
  
 `pdwAttr`  
 [out] Puntatore ai flag di attributo associato al parametro.  
  
 `pdwCPlusTypeFlag`  
 [out] Un puntatore a un flag che specifica che il parametro è un <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Puntatore a una costante stringa restituita dal parametro.  
  
 `pcchValue`  
 [out] Le dimensioni di `ppValue` in caratteri "wide", oppure zero se `ppValue` non contiene una stringa.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** inclusa come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
