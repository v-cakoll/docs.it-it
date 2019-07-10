---
title: Metodo IMetaDataAssemblyImport::GetAssemblyProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyProps
helpviewer_keywords:
- GetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetAssemblyProps method [.NET Framework metadata]
ms.assetid: 0eaa4aa9-9441-444a-920c-e4b2a2db899e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ec04588bd1cc21e585d89c734c152a86fb835b15
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772726"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>Metodo IMetaDataAssemblyImport::GetAssemblyProps
Ottiene il set di proprietà per l'assembly con la firma dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
HRESULT GetAssemblyProps (  
    [in]  mdAssembly          mda,  
    [out] const void          **ppbPublicKey,   
    [out] ULONG               *pcbPublicKey,  
    [out] ULONG               *pulHashAlgId,  
    [out] LPWSTR              szName,  
    [in] ULONG                cchName,  
    [out] ULONG               *pchName,  
    [out] ASSEMBLYMETADATA    *pMetaData,  
    [out] DWORD               *pdwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a>Parametri  
 `mda`  
 [in]. Il `mdAssembly` token di metadati che rappresenta l'assembly per cui ottenere le proprietà.  
  
 `ppbPublicKey`  
 [out] Puntatore alla chiave pubblica o token di metadati.  
  
 `pcbPublicKey`  
 [out] Il numero di byte nella chiave pubblica restituita.  
  
 `pulHashAlgId`  
 [out] Un puntatore all'algoritmo utilizzato per eseguire l'hashing i file nell'assembly.  
  
 `szName`  
 [out] Il nome semplice dell'assembly.  
  
 `cchName`  
 [in] Le dimensioni, in caratteri wide, di `szName`.  
  
 `pchName`  
 [out] Numero di caratteri wide effettivamente restituiti nella `szName`.  
  
 `pMetaData`  
 [out] Un puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.  
  
 `pdwAssemblyFlags`  
 [out] Flag che descrivono i metadati applicati a un assembly. Questo valore è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
