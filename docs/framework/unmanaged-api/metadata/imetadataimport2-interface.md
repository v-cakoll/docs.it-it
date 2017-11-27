---
title: Interfaccia IMetaDataImport2
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2
helpviewer_keywords: IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1b00879f1d22d49e5f0dc3bdb072e0545feda68d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2-interface"></a>Interfaccia IMetaDataImport2
Estende il [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaccia per consentire l'utilizzo dei tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[EnumGenericParamConstraints (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|Ottiene un enumeratore per una matrice di vincoli del parametro generico associato al parametro generico rappresentato dal token specificato.|  
|[EnumGenericParams (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|Ottiene un enumeratore per una matrice di token di parametri generici associati il TypeDef o MethodDef specificato token.|  
|[EnumMethodSpecs (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|Ottiene un enumeratore per una matrice di MethodSpec token associato al specificato MethodDef o MemberRef token.|  
|[GetGenericParamConstraintProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.|  
|[GetGenericParamProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|Ottiene i metadati associati al parametro generico rappresentato dal token specificato.|  
|[GetMethodSpecProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|Ottiene la firma dei metadati del metodo di MethodSpec specificato a cui fa riferimento token.|  
|[GetPEKind (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|Ottiene un valore che identifica il tipo di codice in un file eseguibile portabile (PE) di file, in genere un file DLL o EXE, definito nell'ambito dei metadati corrente|  
|[GetVersionString (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|Ottiene il numero di versione del runtime che è stato utilizzato per compilare l'assembly.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 <xref:System.Reflection.PortableExecutableKinds>  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataImport (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
