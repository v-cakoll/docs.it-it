---
title: Interfaccia IMetaDataConverter
ms.date: 03/30/2017
api_name:
- IMetaDataConverter
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataConverter
helpviewer_keywords:
- IMetaDataConverter interface [.NET Framework metadata]
ms.assetid: 9caea662-0167-4267-b14a-2fa42c3be4ea
topic_type:
- apiref
ms.openlocfilehash: 7a2a5080872f49a84e36c53ac337d91738c15e45
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501339"
---
# <a name="imetadataconverter-interface"></a>Interfaccia IMetaDataConverter
Fornisce metodi per eseguire il mapping delle librerie dei tipi alle relative firme di metadati e per eseguire la conversione da una all'altra.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo GetMetaDataFromTypeInfo](imetadataconverter-getmetadatafromtypeinfo-method.md)|Ottiene un puntatore a un'istanza di [IMetaDataImport](imetadataimport-interface.md) che rappresenta la firma dei metadati per la libreria dei tipi a cui fa riferimento l' `ITypeInfo` istanza specificata.|  
|[Metodo GetMetaDataFromTypeLib](imetadataconverter-getmetadatafromtypelib-method.md)|Ottiene un puntatore a un' `IMetaDataImport` istanza di che rappresenta la firma dei metadati per la libreria dei tipi rappresentata dall'istanza di specificata `ITypeLib` .|  
|[Metodo GetTypeLibFromMetaData](imetadataconverter-gettypelibfrommetadata-method.md)|Ottiene un puntatore a un' `ITypeLib` istanza di che rappresenta la libreria dei tipi con i nomi di modulo e di libreria specificati.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforma:** Vedere [requisiti di sistema](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
