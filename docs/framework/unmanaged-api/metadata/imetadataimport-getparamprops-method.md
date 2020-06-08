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
ms.openlocfilehash: c2abf2813c6e1a9db4264bded32d9cb9c58a2bcb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84491056"
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
 in Dimensioni richieste in caratteri wide di `szName` .  
  
 `pchName`  
 out Dimensione restituita in caratteri wide di `szName` .  
  
 `pdwAttr`  
 out Puntatore a qualsiasi flag di attributo associato al parametro. Si tratta di una maschera di maschera di `CorParamAttr` valori.  
  
 `pdwCPlusTypeFlag`  
 out Puntatore a un flag che specifica che il parametro è un oggetto <xref:System.ValueType> .  
  
 `ppValue`  
 out Puntatore a una stringa costante restituita dal parametro.  
  
 `pcchValue`  
 out Dimensioni di `ppValue` in caratteri wide oppure zero se non `ppValue` dispone di una stringa.  
  
## <a name="remarks"></a>Osservazioni

I valori di sequenza in `pulSequence` iniziano con 1 per i parametri. Il numero di sequenza di un valore restituito è 0.

## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Incluso come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
- [Interfaccia IMetaDataImport2](imetadataimport2-interface.md)
