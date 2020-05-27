---
title: Metodo IMetaDataAssemblyEmit::DefineManifestResource
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineManifestResource
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type:
- apiref
ms.openlocfilehash: 026f5efe195cdb34999b65c5f47de6f68d30e11a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008131"
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>Metodo IMetaDataAssemblyEmit::DefineManifestResource
Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,
    [in] mdToken                tkImplementation,
    [in] DWORD                  dwOffset,
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `szName`  
 [in] Nome della risorsa.  
  
 `tkImplementation`  
 in Token di metadati di tipo `mdtFile` o `mdtAssemblyRef` che esegue il mapping al provider di risorse. Un valore NULL indica che il file in cui sono incorporati i metadati è il provider di risorse.  
  
 `dwOffset`  
 in Offset all'inizio della risorsa all'interno del file. Per le risorse in file autonomi, questo valore sarà sempre zero. Se la risorsa è incorporata in un file PE (Portable Executable), si tratta di un offset del BLOB di risorse, che inizia in corrispondenza della posizione specificata nel file di intestazione cor. h.  
  
 `dwResourceFlags`  
 in Combinazione bit per bit di valori di flag che specificano le impostazioni delle proprietà per la definizione di risorsa.  
  
 `pmdmr`  
 out Puntatore al token di metadati restituito.  
  
## <a name="remarks"></a>Commenti  
 `ManifestResource`È necessario definire una struttura di metadati per ogni risorsa implementata in ognuno dei file dell'assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
