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
ms.openlocfilehash: bb73ccdd9eee4b5a655a56b5d6757e0c6003fbc9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437121"
---
# <a name="imetadataimportgetparamprops-method"></a>Metodo IMetaDataImport::GetParamProps
Ottiene i valori di metadati relativi al parametro a cui fa riferimento il token ParamDef specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
 in Token ParamDef che rappresenta il parametro per il quale restituire i metadati.  
  
 `pmd`  
 out Puntatore a un token MethodDef che rappresenta il metodo che accetta il parametro.  
  
 `pulSequence`  
 out Posizione ordinale del parametro nell'elenco di argomenti del metodo.  
  
 `szName`  
 out Buffer in cui memorizzare il nome del parametro.  
  
 `cchName`  
 in Dimensioni richieste in caratteri wide di `szName`.  
  
 `pchName`  
 out Dimensioni restituite in caratteri wide di `szName`.  
  
 `pdwAttr`  
 out Puntatore a qualsiasi flag di attributo associato al parametro. Si tratta di una maschera di maschera dei valori `CorParamAttr`.  
  
 `pdwCPlusTypeFlag`  
 out Puntatore a un flag che specifica che il parametro è un <xref:System.ValueType>.  
  
 `ppValue`  
 out Puntatore a una stringa costante restituita dal parametro.  
  
 `pcchValue`  
 out Dimensioni del `ppValue` di caratteri wide oppure zero se `ppValue` non dispone di una stringa.  
  
## <a name="remarks"></a>Note

I valori di sequenza in `pulSequence` iniziano con 1 per i parametri. Il numero di sequenza di un valore restituito è 0.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
