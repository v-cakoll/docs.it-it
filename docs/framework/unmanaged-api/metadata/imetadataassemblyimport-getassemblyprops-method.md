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
ms.openlocfilehash: 911d0d1444e2cf3cb8241eeeff63a5a86b4ab806
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33446274"
---
# <a name="imetadataassemblyimportgetassemblyprops-method"></a>Metodo IMetaDataAssemblyImport::GetAssemblyProps
Ottiene il set di proprietà per l'assembly con la firma dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
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
  
#### <a name="parameters"></a>Parametri  
 `mda`  
 [in]. Il `mdAssembly` token di metadati che rappresenta l'assembly per cui ottenere le proprietà.  
  
 `ppbPublicKey`  
 [out] Un puntatore a chiave pubblica o token di metadati.  
  
 `pcbPublicKey`  
 [out] Il numero di byte in una chiave pubblica restituita.  
  
 `pulHashAlgId`  
 [out] Un puntatore per l'algoritmo di hash file nell'assembly.  
  
 `szName`  
 [out] Il nome semplice dell'assembly.  
  
 `cchName`  
 [in] La dimensione in caratteri wide, di `szName`.  
  
 `pchName`  
 [out] Numero di caratteri "wide" effettivamente restituiti nella `szName`.  
  
 `pMetaData`  
 [out] Un puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.  
  
 `pdwAssemblyFlags`  
 [out] Flag che descrivono i metadati applicati a un assembly. Questo valore è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
