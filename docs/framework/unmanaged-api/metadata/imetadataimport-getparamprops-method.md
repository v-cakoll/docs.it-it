---
title: Metodo IMetaDataImport::GetParamProps
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ac8efed8c0a905d2cfad433348a99fe578eeae
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61777624"
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
  
## <a name="parameters"></a>Parametri  
 `tk`  
 [in] Token ParamDef che rappresenta il parametro per restituire i metadati.  
  
 `pmd`  
 [out] Un puntatore a un token MethodDef che rappresentano il metodo che accetta il parametro.  
  
 `pulSequence`  
 [out] La posizione ordinale del parametro nell'elenco di argomenti di metodo.  
  
 `szName`  
 [out] Un buffer contenente il nome del parametro.  
  
 `cchName`  
 [in] Le dimensioni richieste in caratteri wide di `szName`.  
  
 `pchName`  
 [out] Le dimensioni restituite in caratteri wide di `szName`.  
  
 `pdwAttr`  
 [out] Puntatore ai flag di attributo associato al parametro. Si tratta di una maschera di bit delle `CorParamAttr` valori.  
  
 `pdwCPlusTypeFlag`  
 [out] Un puntatore a un flag che specifica che il parametro è un <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Puntatore a una costante stringa restituita dal parametro.  
  
 `pcchValue`  
 [out] Il valore pari `ppValue` in caratteri "wide", oppure zero se `ppValue` non contiene una stringa.  
  
## <a name="remarks"></a>Note

La sequenza di valori in `pulSequence` iniziano da 1 per i parametri. Valore restituito è un numero di sequenza pari a 0.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Inclusa come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
