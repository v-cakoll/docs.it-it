---
title: Interfaccia IMetaDataConverter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataConverter
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataConverter
helpviewer_keywords: IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f551a774a860f595cc90a7cca9eee2c726ef50ee
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataconverter-interface"></a>Interfaccia IMetaDataConverter
Fornisce metodi per eseguire il mapping delle librerie dei tipi alle relative firme di metadati e per eseguire la conversione da una all'altra.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[GetMetaDataFromTypeInfo (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypeinfo-method.md)|Ottiene un puntatore a un [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) istanza che rappresenta la firma dei metadati per la libreria dei tipi a cui fa riferimento specificato `ITypeInfo` istanza.|  
|[GetMetaDataFromTypeLib (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-getmetadatafromtypelib-method.md)|Ottiene un puntatore a un `IMetaDataImport` istanza che rappresenta la firma dei metadati per la libreria dei tipi rappresentata dall'oggetto `ITypeLib` istanza.|  
|[GetTypeLibFromMetaData (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataconverter-gettypelibfrommetadata-method.md)|Ottiene un puntatore a un `ITypeLib` istanza che rappresenta la libreria dei tipi con i nomi di modulo e la libreria specificati.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
