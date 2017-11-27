---
title: Interfaccia IMetaDataEmit
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit
helpviewer_keywords: IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b62e11f8237330122ccd2bd8775f8d113545dd95
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit-interface"></a>Interfaccia IMetaDataEmit
Fornisce metodi per creare, modificare e salvare i metadati sull'assembly nell'ambito attualmente definito. I metadati possono essere archiviato in memoria o salvati su disco.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[ApplyEditAndContinue (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Aggiorna l'ambito dell'assembly corrente con le modifiche apportate nell'oggetto specificato `pImport`.|  
|[DefineCustomAttribute (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Crea una definizione per un attributo personalizzato con la firma dei metadati specificato, per collegare l'oggetto specificato e ottiene un token per tale definizione di attributo personalizzato.|  
|[DefineEvent (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Crea una definizione per un evento con la firma dei metadati specificati e ottiene un token per tale definizione di evento.|  
|[DefineField (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Crea una definizione per un campo con la firma dei metadati specificati e ottiene un token per tale definizione.|  
|[DefineImportMember (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Crea una definizione per un membro di un tipo definito in un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione.|  
|[DefineImportType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Crea una definizione per un riferimento a un tipo definito in un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione.|  
|[DefineMemberRef (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Crea una definizione per un riferimento a un membro di un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione.|  
|[DefineMethod (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Crea una definizione per un metodo con la firma specificata e restituisce un token per tale definizione.|  
|[DefineMethodImpl (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Crea una definizione per l'implementazione di un metodo ereditato da un'interfaccia e restituisce un token per tale definizione di implementazione del metodo.|  
|[DefineModuleRef (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Crea la firma dei metadati per un modulo con il nome specificato.|  
|[DefineNestedType (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Crea la firma dei metadati di una definizione di tipo e restituisce un `mdTypeDef` token per tale tipo, specifica inoltre che il tipo definito è un membro del tipo a cui fa riferimento `tdEncloser`.|  
|[DefineParam (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Crea una definizione di parametro con la firma specificata per il metodo a cui fa riferimento il token specificato e ottiene un token per la definizione di parametro.|  
|[DefinePermissionSet (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Crea una definizione per un set di autorizzazioni con la firma dei metadati specificati e ottiene un token per tale definizione di set di autorizzazioni.|  
|[DefinePinvokeMap (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Imposta le funzionalità di firma PInvoke del metodo a cui fa riferimento il token specificato.|  
|[DefineProperty (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Crea una definizione di proprietà per il tipo specificato, con l'oggetto specificato `get` e `set` funzioni di accesso, metodo e ottiene un token per tale definizione.|  
|[DefineSecurityAttributeSet (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Crea un set di autorizzazioni di sicurezza di collegare l'oggetto a cui fa riferimento il token specificato.|  
|[DefineTypeDef (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Crea una definizione di tipo per un tipo common language runtime e ottiene un token di metadati per la definizione del tipo.|  
|[DefineTypeRefByName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Ottiene i metadati di un token per un tipo definito in un altro modulo all'esterno dell'ambito corrente.|  
|[DefineUserString (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Ottiene i metadati token per la stringa letterale specificata.|  
|[DeleteClassLayout (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Elimina definitivamente la firma dei metadati di layout di classe per il tipo a cui fa riferimento il token specificato.|  
|[DeleteFieldMarshal (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Elimina definitivamente il PInvoke marshalling firma dei metadati per l'oggetto a cui fa riferimento il token specificato.|  
|[DeletePinvokeMap (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Elimina i metadati di mapping PInvoke per l'oggetto a cui fa riferimento il token specificato.|  
|[DeleteToken (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Elimina il token specificato dall'ambito dei metadati corrente.|  
|[GetSaveSize (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Ottiene le dimensioni stimate binaria dell'assembly nell'ambito corrente.|  
|[GetTokenFromSig (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Ottiene un token per la firma dei metadati specificato.|  
|[GetTokenFromTypeSpec (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Ottiene i metadati di un token per il tipo con la firma dei metadati specificato.|  
|[Merge (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.|  
|[MergeEnd (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Unisce in corrente ambito tutti gli ambiti dei metadati specificati da uno o più chiamate precedenti a `IMetaDataEmit::Merge`.|  
|[Save (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Salva tutti i metadati nell'ambito corrente del file all'indirizzo specificato.|  
|[SaveToMemory (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Salva tutti i metadati nell'ambito corrente per l'area specificata di memoria.|  
|[SaveToStream (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Salva tutti i metadati nell'ambito corrente specificato `IStream`.|  
|[SetClassLayout (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Imposta o aggiorna la firma di un tipo definito da una chiamata precedente al layout della classe `IMetaDataEmit::DefineTypeDef`.|  
|[SetCustomAttributeValue (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Imposta o aggiorna il valore di un attributo personalizzato definito tramite una chiamata precedente a `IMetaDataEmit::DefineCustomAttribute`.|  
|[SetEventProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Imposta o aggiorna la funzionalità specificata di un evento definito tramite una chiamata precedente a `IMetaDataEmit::DefineEvent`.|  
|[SetFieldMarshal (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Imposta le informazioni di marshalling per il parametro di campo, metodo o un metodo a cui fa riferimento il token specificato di PInvoke.|  
|[SetFieldProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Imposta o aggiorna il valore predefinito per il campo a cui fa riferimento il token di campo specificato.|  
|[SetFieldRVA (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Imposta un valore della variabile globale per l'indirizzo virtuale relativo del campo a cui fa riferimento il token specificato.|  
|[SetHandler (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Imposta il metodo a cui fa riferimento specificato `IUnknown` puntatore come un callback di notifica per i nuovi mapping token.|  
|[Metodo SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Imposta o aggiorna la firma dei metadati di implementazione del metodo ereditato a cui fa riferimento il token specificato.|  
|[SetMethodProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Imposta o aggiorna la funzione, archiviata nell'indirizzo virtuale relativo specificato, di un metodo definito da una precedente chiamata a `IMetaDataEmit::DefineMethod`.|  
|[SetModuleProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Aggiorna i riferimenti a un modulo definito da una precedente chiamata a `IMetaDataEmit::DefineModuleRef`.|  
|[SetParamProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Imposta o modifica le funzioni di un parametro di metodo che è stato definito da una precedente chiamata a `IMetaDataEmit::DefineParam`.|  
|[SetParent (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Stabilisce che il membro specificato, come definito da una precedente chiamata a `IMetaDataEmit::DefineMemberRef`, è un membro del tipo specificato, come definito da una precedente chiamata a `IMetaDataEmit::DefineTypeDef`.|  
|[SetPermissionSetProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Imposta o aggiorna le funzionalità di firma dei metadati di un set definito da una precedente chiamata a `IMetaDataEmit::DefinePermissionSet`.|  
|[SetPinvokeMap (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Imposta o modifica le funzionalità di firma del metodo PInvoke, come definito da una precedente chiamata a `IMetaDataEmit::DefinePinvokeMap`.|  
|[SetPropertyProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Imposta le funzioni archiviate nei metadati per una proprietà definita da una precedente chiamata a `IMetaDataEmit::DefineProperty`.|  
|[SetRVA (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Imposta l'indirizzo virtuale relativo del metodo specificato.|  
|[SetTypeDefProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Imposta le funzionalità di un tipo definito da una precedente chiamata a `IMetaDataEmit::DefineTypeDef`.|  
|[TranslateSigWithScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito unito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
