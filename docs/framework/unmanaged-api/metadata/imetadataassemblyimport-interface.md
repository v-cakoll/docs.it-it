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
ms.openlocfilehash: 2a67f50fa1042e8d3957a9a0394507f260a328c6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009015"
---
# <a name="imetadataassemblyimport-interface"></a>Interfaccia IMetaDataAssemblyImport
Fornisce metodi per accedere ed esaminare il contenuto di un manifesto dell'assembly.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo CloseEnum](imetadataassemblyimport-closeenum-method.md)|Rilascia l'handle all'enumeratore specificato.|  
|[Metodo EnumAssemblyRefs](imetadataassemblyimport-enumassemblyrefs-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdAssemblyRef` token degli assembly a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumExportedTypes](imetadataassemblyimport-enumexportedtypes-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdExportedType` token dei tipi com a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumFiles](imetadataassemblyimport-enumfiles-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdFile` token dei file a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo EnumManifestResources](imetadataassemblyimport-enummanifestresources-method.md)|Ottiene un puntatore a interfaccia a un enumeratore che contiene i `mdManifestResource` token delle risorse a cui fa riferimento l'assembly nell'ambito dei metadati corrente.|  
|[Metodo FindAssembliesByName](imetadataassemblyimport-findassembliesbyname-method.md)|Ottiene una matrice di `mdAssemblyRef` token per gli assembly con il nome specificato.|  
|[Metodo FindExportedTypeByName](imetadataassemblyimport-findexportedtypebyname-method.md)|Ottiene un `mdExportedType` token per il tipo com con il nome specificato.|  
|[Metodo FindManifestResourceByName](imetadataassemblyimport-findmanifestresourcebyname-method.md)|Ottiene un `mdManifestResource` token per la risorsa con il nome specificato.|  
|[Metodo GetAssemblyFromScope](imetadataassemblyimport-getassemblyfromscope-method.md)|Ottiene il token per l'assembly nell'ambito dei metadati corrente.|  
|[Metodo GetAssemblyProps](imetadataassemblyimport-getassemblyprops-method.md)|Ottiene le impostazioni delle proprietà dell'assembly specificato.|  
|[Metodo GetAssemblyRefProps](imetadataassemblyimport-getassemblyrefprops-method.md)|Ottiene le impostazioni della proprietà del `mdAssemblyRef` token specificato.|  
|[Metodo GetExportedTypeProps](imetadataassemblyimport-getexportedtypeprops-method.md)|Ottiene le impostazioni della proprietà del tipo COM specificato.|  
|[Metodo GetFileProps](imetadataassemblyimport-getfileprops-method.md)|Ottiene le impostazioni della proprietà del file specificato.|  
|[Metodo GetManifestResourceProps](imetadataassemblyimport-getmanifestresourceprops-method.md)|Ottiene le impostazioni della proprietà della risorsa di manifesto specificata.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataAssemblyEmit](imetadataassemblyemit-interface.md)
