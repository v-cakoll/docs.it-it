---
title: Interfaccia IMetaDataImport2
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: 0fd7915ef46899bdce8312bc6e8a466167e26382
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429203"
---
# <a name="imetadataimport2-interface"></a>Interfaccia IMetaDataImport2
Estende l'interfaccia [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) per fornire la funzionalità di utilizzo di tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumGenericParamConstraints](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparamconstraints-method.md)|Ottiene un enumeratore per una matrice di vincoli di parametri generici associati al parametro generico rappresentato dal token specificato.|  
|[Metodo EnumGenericParams](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enumgenericparams-method.md)|Ottiene un enumeratore per una matrice di token di parametro generici associati al token TypeDef o MethodDef specificato.|  
|[Metodo EnumMethodSpecs](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-enummethodspecs-method.md)|Ottiene un enumeratore per una matrice di token MethodSpec associati al token MethodDef o MemberRef specificato.|  
|[Metodo GetGenericParamConstraintProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamconstraintprops-method.md)|Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.|  
|[Metodo GetGenericParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getgenericparamprops-method.md)|Ottiene i metadati associati al parametro generico rappresentato dal token specificato.|  
|[Metodo GetMethodSpecProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getmethodspecprops-method.md)|Ottiene la firma dei metadati del metodo a cui fa riferimento il token MethodSpec specificato.|  
|[Metodo GetPEKind](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)|Ottiene un valore che identifica la natura del codice in un file eseguibile portabile (PE, Portable Executable), in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.|  
|[Metodo GetVersionString](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getversionstring-method.md)|Ottiene il numero di versione del runtime utilizzato per compilare l'assembly.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.PortableExecutableKinds>
- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
