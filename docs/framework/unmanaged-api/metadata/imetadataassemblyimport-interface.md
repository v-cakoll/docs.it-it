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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9f213bcb9f87c34d23b53c2016bd841aae7c7194
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54540276"
---
# <a name="imetadataassemblyimport-interface"></a>Interfaccia IMetaDataAssemblyImport
Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CloseEnum](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Rilascia l'handle per l'enumeratore specificato.|  
|[Metodo EnumAssemblyRefs](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdAssemblyRef` token degli assembly a cui fatto riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumExportedTypes](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdExportedType` i token dei tipi COM a cui fatto riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumFiles](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdFile` token dei file a cui fatto riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumManifestResources](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Ottiene un puntatore a interfaccia per un enumeratore che contiene il `mdManifestResource` token delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo FindAssembliesByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Ottiene una matrice di `mdAssemblyRef` i token per gli assembly con il nome specificato.|  
|[Metodo FindExportedTypeByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Ottiene un `mdExportedType` token per il tipo COM con il nome specificato.|  
|[Metodo FindManifestResourceByName](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Ottiene un `mdManifestResource` token per la risorsa con il nome specificato.|  
|[Metodo GetAssemblyFromScope](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Ottiene il token per l'assembly nell'ambito dei metadati corrente.|  
|[Metodo GetAssemblyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Ottiene le impostazioni delle proprietà dell'assembly specificato.|  
|[Metodo GetAssemblyRefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Ottiene le impostazioni delle proprietà dell'oggetto specificato `mdAssemblyRef` token.|  
|[Metodo GetExportedTypeProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Ottiene le impostazioni delle proprietà del tipo COM specificato.|  
|[Metodo GetFileProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Ottiene le impostazioni delle proprietà del file specificato.|  
|[Metodo GetManifestResourceProps](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Ottiene le impostazioni delle proprietà della risorsa del manifesto specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
