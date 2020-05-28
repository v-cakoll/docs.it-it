---
title: Metodo IMetaDataAssemblyImport::FindManifestResourceByName
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindManifestResourceByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindManifestResourceByName
helpviewer_keywords:
- FindManifestResourceByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindManifestResourceByName method [.NET Framework metadata]
ms.assetid: 7b72fa11-3866-402b-bdea-2b966b77cfe0
topic_type:
- apiref
ms.openlocfilehash: ef6f7a1a6e86b45acce91792385bc3761dfb4c39
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009080"
---
# <a name="imetadataassemblyimportfindmanifestresourcebyname-method"></a>Metodo IMetaDataAssemblyImport::FindManifestResourceByName
Ottiene un puntatore alla risorsa del manifesto con il nome specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT FindManifestResourceByName (  
    [in]  LPCWSTR                szName,
    [out] mdManifestResource     *ptkManifestResource  
);
```  
  
## <a name="parameters"></a>Parametri  
 `szName`  
 [in] Nome della risorsa.  
  
 `ptkManifestResource`  
 out Matrice utilizzata per archiviare i `mdManifestResource` token di metadati, ognuno dei quali rappresenta una risorsa di manifesto.  
  
## <a name="remarks"></a>Commenti  
 Il `FindManifestResourceByName` metodo utilizza le regole standard utilizzate dal Common Language Runtime per la risoluzione dei riferimenti.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
- [Modalità di individuazione degli assembly da parte del runtime](../../deployment/how-the-runtime-locates-assemblies.md)
