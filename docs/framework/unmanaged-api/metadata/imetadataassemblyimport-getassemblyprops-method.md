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
ms.openlocfilehash: a90deaf3e9ddf326c6fca558cbb4681fc40e022d
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009054"
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
 [in]. `mdAssembly`Token di metadati che rappresenta l'assembly per il quale ottenere le proprietà.  
  
 `ppbPublicKey`  
 out Puntatore alla chiave pubblica o al token di metadati.  
  
 `pcbPublicKey`  
 out Numero di byte nella chiave pubblica restituita.  
  
 `pulHashAlgId`  
 out Puntatore all'algoritmo utilizzato per eseguire l'hashing dei file nell'assembly.  
  
 `szName`  
 out Nome semplice dell'assembly.  
  
 `cchName`  
 in Dimensione, in caratteri wide, di `szName` .  
  
 `pchName`  
 out Numero di caratteri wide effettivamente restituiti in `szName` .  
  
 `pMetaData`  
 out Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.  
  
 `pdwAssemblyFlags`  
 out Flag che descrivono i metadati applicati a un assembly. Questo valore è una combinazione di uno o più valori [CorAssemblyFlags](corassemblyflags-enumeration.md) .  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
