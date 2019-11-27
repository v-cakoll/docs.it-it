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
ms.openlocfilehash: 83170815f4aa65988bb6a6394bd466a0ba376ebf
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432060"
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
 in Nome della risorsa.  
  
 `tkImplementation`  
 in Token di metadati di tipo `mdtFile` o `mdtAssemblyRef` che esegue il mapping al provider di risorse. Un valore NULL indica che il file in cui sono incorporati i metadati è il provider di risorse.  
  
 `dwOffset`  
 in Offset all'inizio della risorsa all'interno del file. Per le risorse in file autonomi, questo valore sarà sempre zero. Se la risorsa è incorporata in un file PE (Portable Executable), si tratta di un offset del BLOB di risorse, che inizia in corrispondenza della posizione specificata nel file di intestazione cor. h.  
  
 `dwResourceFlags`  
 in Combinazione bit per bit di valori di flag che specificano le impostazioni delle proprietà per la definizione di risorsa.  
  
 `pmdmr`  
 out Puntatore al token di metadati restituito.  
  
## <a name="remarks"></a>Note  
 È necessario definire una `ManifestResource` struttura dei metadati per ogni risorsa implementata in ognuno dei file dell'assembly.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
