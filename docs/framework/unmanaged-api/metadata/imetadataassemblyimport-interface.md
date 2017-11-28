---
title: Interfaccia IMetaDataAssemblyImport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyImport
helpviewer_keywords: IMetaDataAssemblyImport interface [.NET Framework metadata]
ms.assetid: 29c6fba5-4cea-417d-b484-7ed22ebff1c9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ef5b913dc9b1391c63cb123e1f922ca61da6a5bb
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataassemblyimport-interface"></a>Interfaccia IMetaDataAssemblyImport
Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CloseEnum (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-closeenum-method.md)|Rilascia l'handle per l'enumeratore specificato.|  
|[EnumAssemblyRefs (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumassemblyrefs-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdAssemblyRef` token degli assembly a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[EnumExportedTypes (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumexportedtypes-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdExportedType` token dei tipi COM a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[EnumFiles (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enumfiles-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdFile` token dei file a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[EnumManifestResources (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-enummanifestresources-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene il `mdManifestResource` token delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[FindAssembliesByName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findassembliesbyname-method.md)|Ottiene una matrice di `mdAssemblyRef` token per gli assembly con il nome specificato.|  
|[FindExportedTypeByName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findexportedtypebyname-method.md)|Ottiene un `mdExportedType` token per il tipo COM con il nome specificato.|  
|[FindManifestResourceByName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-findmanifestresourcebyname-method.md)|Ottiene un `mdManifestResource` token per la risorsa con il nome specificato.|  
|[GetAssemblyFromScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyfromscope-method.md)|Ottiene il token per l'assembly nell'ambito dei metadati corrente.|  
|[GetAssemblyProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyprops-method.md)|Ottiene le impostazioni delle proprietà dell'assembly specificato.|  
|[GetAssemblyRefProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getassemblyrefprops-method.md)|Ottiene le impostazioni delle proprietà dell'oggetto specificato `mdAssemblyRef` token.|  
|[GetExportedTypeProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getexportedtypeprops-method.md)|Ottiene le impostazioni delle proprietà del tipo COM specificato.|  
|[GetFileProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getfileprops-method.md)|Ottiene le impostazioni delle proprietà del file specificato.|  
|[GetManifestResourceProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-getmanifestresourceprops-method.md)|Ottiene le impostazioni delle proprietà della risorsa del manifesto specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [Interfaccia IMetaDataAssemblyEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
