---
title: Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175967"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a>Metodo IMetaDataAssemblyImport::GetAssemblyRefProps
Ottiene il set di proprietà per il riferimento all'assembly con la firma dei metadati specificata.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp  
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
  
## <a name="parameters"></a>Parametri  
 `mdar`  
 [in] Token `mdAssemblyRef` di metadati che rappresenta il riferimento all'assembly per il quale ottenere le proprietà.  
  
 `ppbPublicKeyOrToken`  
 [fuori] Puntatore alla chiave pubblica o al token di metadati.  
  
 `pcbPublicKeyOrToken`  
 [fuori] Numero di byte nella chiave pubblica o nel token restituito.  
  
 `szName`  
 [fuori] Nome semplice dell'assembly.  
  
 `cchName`  
 [in] La dimensione, in caratteri `szName`ampi, di .  
  
 `pchName`  
 [fuori] Puntatore al numero di caratteri wide `szName`effettivamente restituiti in .  
  
 `pMetaData`  
 [fuori] Puntatore a una struttura ASSEMBLYMETADATA che contiene i metadati dell'assembly.  
  
 `ppbHashValue`  
 [fuori] Puntatore al valore hash. Si tratta dell'hash, utilizzando l'algoritmo `PublicKey` SHA-1, della proprietà dell'assembly a cui si fa riferimento, a meno che non sia impostato il flag arfFullOriginator dell'enumerazione [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) .  
  
 `pcbHashValue`  
 [fuori] Numero di caratteri wide nel valore hash restituito.  
  
 `pdwAssemblyRefFlags`  
 [fuori] Puntatore a flag che descrivono i metadati applicati a un assembly. Il valore flags è una combinazione di uno o più [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) valori.  
  
## <a name="return-value"></a>Valore restituito  
 Questo metodo restituisce S_OK se ha esito positivo; in caso contrario, restituisce uno dei codici di errore definiti nel file di intestazione Winerror.h.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor.h  
  
 **Biblioteca:** Utilizzato come risorsa in MsCorEE.dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
