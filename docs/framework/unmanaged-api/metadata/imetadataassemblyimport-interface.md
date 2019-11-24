---
title: Interfaccia IMetaDataAssemblyImport
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport
helpviewer_keywords:
- IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type:
- apiref
ms.openlocfilehash: 289e26868ff2eb9e1d97cf084e9a888815062ea4
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436302"
---
# <a name="imetadataassemblyimport-interface"></a>Interfaccia IMetaDataAssemblyImport
Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CloseEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Rilascia l'handle all'enumeratore specificato.|  
|[Metodo EnumAssemblyRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i token `mdAssemblyRef` degli assembly a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumExportedTypes](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i token di `mdExportedType` dei tipi COM a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumFiles](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i token di `mdFile` dei file a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumManifestResources](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i token di `mdManifestResource` delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo FindAssembliesByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Ottiene una matrice di token `mdAssemblyRef` per gli assembly con il nome specificato.|  
|[Metodo FindExportedTypeByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Ottiene un token di `mdExportedType` per il tipo COM con il nome specificato.|  
|[Metodo FindManifestResourceByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Ottiene un token di `mdManifestResource` per la risorsa con il nome specificato.|  
|[Metodo GetAssemblyFromScope](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Ottiene il token per l'assembly nell'ambito dei metadati corrente.|  
|[Metodo GetAssemblyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Ottiene le impostazioni delle proprietà dell'assembly specificato.|  
|[Metodo GetAssemblyRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Ottiene le impostazioni della proprietà del token di `mdAssemblyRef` specificato.|  
|[Metodo GetExportedTypeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Ottiene le impostazioni della proprietà del tipo COM specificato.|  
|[Metodo GetFileProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Ottiene le impostazioni della proprietà del file specificato.|  
|[Metodo GetManifestResourceProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Ottiene le impostazioni della proprietà della risorsa di manifesto specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
