---
title: Interfaccia IMetaDataAssemblyEmit
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit
helpviewer_keywords:
- IMetaDataAssemblyEmit interface [.NET Framework metadata]
ms.assetid: 34fb03cc-2285-4a45-ac48-ad993b7a921a
topic_type:
- apiref
ms.openlocfilehash: 807e1ee831a43a4ef1e7b0a269ee38131f24081e
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008118"
---
# <a name="imetadataassemblyemit-interface"></a>Interfaccia IMetaDataAssemblyEmit
Fornisce metodi che supportano il modello autodescrittivo impiegato da Common Language Runtime per la risoluzione e l'uso delle risorse.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo DefineAssembly](imetadataassemblyemit-defineassembly-method.md)|Crea una struttura dati che contiene i metadati per l'assembly specificato e restituisce il token di metadati associato.|  
|[Metodo DefineAssemblyRef](imetadataassemblyemit-defineassemblyref-method.md)|Crea una struttura `AssemblyRef` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.|  
|[Metodo DefineExportedType](imetadataassemblyemit-defineexportedtype-method.md)|Crea una struttura `ExportedType` che contiene i metadati per il tipo esportato specificato e restituisce il token di metadati associato.|  
|[Metodo DefineFile](imetadataassemblyemit-definefile-method.md)|Crea una struttura dei metadati `File` che contiene i metadati per l'assembly a cui fa riferimento questo assembly e restituisce il token di metadati associato.|  
|[Metodo DefineManifestResource](imetadataassemblyemit-definemanifestresource-method.md)|Crea una struttura `ManifestResource` che contiene i metadati per la risorsa di manifesto specificata e restituisce il token di metadati associato.|  
|[Metodo SetAssemblyProps](imetadataassemblyemit-setassemblyprops-method.md)|Modifica la struttura dei metadati `Assembly` specificata.|  
|[Metodo SetAssemblyRefProps](imetadataassemblyemit-setassemblyrefprops-method.md)|Modifica la struttura dei metadati `AssemblyRef` specificata.|  
|[Metodo SetExportedTypeProps](imetadataassemblyemit-setexportedtypeprops-method.md)|Modifica la struttura dei metadati `ExportedType` specificata.|  
|[Metodo SetFileProps](imetadataassemblyemit-setfileprops-method.md)|Modifica la struttura dei metadati `File` specificata.|  
|[Metodo SetManifestResourceProps](imetadataassemblyemit-setmanifestresourceprops-method.md)|Modifica la struttura dei metadati `ManifestResource` specificata.|  
  
## <a name="remarks"></a>Osservazioni  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataAssemblyImport](imetadataassemblyimport-interface.md)
