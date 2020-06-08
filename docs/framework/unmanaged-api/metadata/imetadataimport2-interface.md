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
ms.openlocfilehash: fe9e87618291218a41e52f80198ce9068c9c56e2
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490394"
---
# <a name="imetadataimport2-interface"></a>Interfaccia IMetaDataImport2
Estende l'interfaccia [IMetaDataImport](imetadataimport-interface.md) per fornire la funzionalità di utilizzo di tipi generici.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo EnumGenericParamConstraints](imetadataimport2-enumgenericparamconstraints-method.md)|Ottiene un enumeratore per una matrice di vincoli di parametri generici associati al parametro generico rappresentato dal token specificato.|  
|[Metodo EnumGenericParams](imetadataimport2-enumgenericparams-method.md)|Ottiene un enumeratore per una matrice di token di parametro generici associati al token TypeDef o MethodDef specificato.|  
|[Metodo EnumMethodSpecs](imetadataimport2-enummethodspecs-method.md)|Ottiene un enumeratore per una matrice di token MethodSpec associati al token MethodDef o MemberRef specificato.|  
|[Metodo GetGenericParamConstraintProps](imetadataimport2-getgenericparamconstraintprops-method.md)|Ottiene i metadati associati al vincolo del parametro generico rappresentato dal token di vincolo specificato.|  
|[Metodo GetGenericParamProps](imetadataimport2-getgenericparamprops-method.md)|Ottiene i metadati associati al parametro generico rappresentato dal token specificato.|  
|[Metodo GetMethodSpecProps](imetadataimport2-getmethodspecprops-method.md)|Ottiene la firma dei metadati del metodo a cui fa riferimento il token MethodSpec specificato.|  
|[Metodo GetPEKind](imetadataimport2-getpekind-method.md)|Ottiene un valore che identifica la natura del codice in un file eseguibile portabile (PE, Portable Executable), in genere un file DLL o EXE, definito nell'ambito dei metadati corrente.|  
|[Metodo GetVersionString](imetadataimport2-getversionstring-method.md)|Ottiene il numero di versione del runtime utilizzato per compilare l'assembly.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Reflection.PortableExecutableKinds>
- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataImport](imetadataimport-interface.md)
