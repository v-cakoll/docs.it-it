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
ms.openlocfilehash: dfa900e2184a8c415d75f5702c572b14c4018749
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177791"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>Metodo IMetaDataAssemblyImport::GetAssemblyProps
Ottiene il set di proprietà per l'assembly con la firma dei metadati specificata.  
  
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
 [in]. Token `mdAssembly` di metadati che rappresenta l'assembly per il quale ottenere le proprietà.  
  
 `ppbPublicKey`  
 [fuori] Puntatore alla chiave pubblica o al token di metadati.  
  
 `pcbPublicKey`  
 [fuori] Numero di byte nella chiave pubblica restituita.  
  
 `pulHashAlgId`  
 [fuori] Puntatore all'algoritmo utilizzato per eseguire l'hashing dei file nell'assembly.  
  
 `szName`  
 [fuori] Nome semplice dell'assembly.  
  
 `cchName`  
 [in] La dimensione, in caratteri `szName`ampi, di .  
  
 `pchName`  
 [fuori] Il numero di caratteri wide `szName`restituiti effettivamente in .  
  
 `pMetaData`  
 [fuori] Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.  
  
 `pdwAssemblyFlags`  
 [fuori] Flag che descrivono i metadati applicati a un assembly. Questo valore è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
