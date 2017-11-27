---
title: Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport.GetAssemblyRefProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9159352c4f7f338c6b9b82ea579ad3cb36c19007
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
Ottiene il set di proprietà per il riferimento all'assembly con la firma dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,   
    [out] const void          **ppbPublicKeyOrToken,   
    [out] ULONG                *pcbPublicKeyOrToken,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] ASSEMBLYMETADATA     *pMetaData,   
    [out] const void           **ppbHashValue,   
    [out] ULONG                *pcbHashValue,   
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mdar`  
 [in] Il `mdAssemblyRef` token di metadati che rappresenta il riferimento all'assembly per cui ottenere le proprietà.  
  
 `ppbPublicKeyOrToken`  
 [out] Un puntatore a chiave pubblica o token di metadati.  
  
 `pcbPublicKeyOrToken`  
 [out] Il numero di byte restituito chiave pubblica o token.  
  
 `szName`  
 [out] Il nome semplice dell'assembly.  
  
 `cchName`  
 [in] La dimensione in caratteri wide, di `szName`.  
  
 `pchName`  
 [out] Un puntatore al numero di caratteri "wide" effettivamente restituiti nella `szName`.  
  
 `pMetaData`  
 [out] Un puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.  
  
 `ppbHashValue`  
 [out] Puntatore al valore hash. Si tratta dell'hash, utilizza l'algoritmo SHA-1, il `PublicKey` proprietà dell'assembly a cui fa riferimento, a meno che il flag arfFullOriginator del [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) set di enumerazione.  
  
 `pcbHashValue`  
 [out] Il numero di caratteri "wide" nel valore hash restituito.  
  
 `pdwAssemblyRefFlags`  
 [out] Puntatore a flag che descrivono i metadati applicati a un assembly. Il valore del flag è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce S_OK se riesce; in caso contrario, restituisce uno dei codici di errore definiti nel file di intestazione Winerror. h.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [IMetaDataAssemblyImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
