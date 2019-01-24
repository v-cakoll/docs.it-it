---
title: Interfaccia IMetaDataEmit
ms.date: 03/30/2017
api_name:
- IMetaDataEmit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit
helpviewer_keywords:
- IMetaDataEmit interface [.NET Framework metadata]
ms.assetid: 3b48fd47-7397-4e2c-8bec-8157aa08978c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f28facc8acb430de4aa255208a62c5fc61f12cd8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54727664"
---
# <a name="imetadataemit-interface"></a>Interfaccia IMetaDataEmit
Fornisce metodi per creare, modificare e salvare i metadati sull'assembly nell'ambito attualmente definito. I metadati possono essere archiviati in memoria o salvato su disco.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Aggiorna l'ambito dell'assembly corrente con le modifiche apportate nell'oggetto specificato `pImport`.|  
|[Metodo DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Crea una definizione per un attributo personalizzato con la firma dei metadati specificato, da associare all'oggetto specificato e ottiene un token per tale definizione di attributo personalizzato.|  
|[Metodo DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Crea una definizione per un evento con la firma dei metadati specificati e ottiene un token di definizione di tale evento.|  
|[Metodo DefineField](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Crea una definizione per un campo con la firma dei metadati specificati e ottiene un token per tale definizione di campo.|  
|[Metodo DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Crea una definizione per un membro di un tipo che viene definito in un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione del riferimento.|  
|[Metodo DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Crea una definizione per un riferimento a un tipo che viene definito in un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione.|  
|[Metodo DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Crea una definizione per un riferimento a un membro di un modulo all'esterno dell'ambito corrente e ottiene un token per tale definizione.|  
|[Metodo DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Crea una definizione per un metodo con la firma specificata e restituisce un token per tale definizione.|  
|[Metodo DefineMethodImpl](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Crea una definizione per l'implementazione di un metodo ereditato da un'interfaccia e restituisce un token per tale definizione di implementazione del metodo.|  
|[Metodo DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Crea la firma dei metadati per un modulo con il nome specificato.|  
|[Metodo DefineNestedType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Crea la firma dei metadati di una definizione di tipo e restituisce un `mdTypeDef` token per quel tipo, specificando inoltre che il tipo definito è un membro del tipo fa riferimento `tdEncloser`.|  
|[Metodo DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Crea una definizione di parametro con la firma specificata per il metodo fa riferimento il token specificato e ottiene un token per la definizione di parametro.|  
|[Metodo DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Crea una definizione per un set di autorizzazioni con la firma dei metadati specificati e ottiene un token per tale definizione del set di autorizzazioni.|  
|[Metodo DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Imposta le funzionalità di firma PInvoke del metodo a cui fa riferimento il token specificato.|  
|[Metodo DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Crea una definizione di proprietà per il tipo specificato, con l'oggetto specificato `get` e `set` funzioni di accesso, metodo e ottiene un token per tale definizione.|  
|[Metodo DefineSecurityAttributeSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Crea un set di autorizzazioni di sicurezza da associare all'oggetto a cui fa riferimento il token specificato.|  
|[Metodo DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Crea una definizione di tipo per un tipo common language runtime e ottiene un token di metadati per tale definizione del tipo.|  
|[Metodo DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Ottiene i metadati di un token per un tipo definito in un altro modulo all'esterno dell'ambito corrente.|  
|[Metodo DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Ottiene i metadati di un token per la stringa letterale specificata.|  
|[Metodo DeleteClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Elimina definitivamente la firma dei metadati di layout di classe per il tipo fa riferimento il token specificato.|  
|[Metodo DeleteFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Elimina definitivamente i PInvoke marshalling firma dei metadati per l'oggetto fa riferimento il token specificato.|  
|[Metodo DeletePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Elimina i metadati di mapping PInvoke per l'oggetto fa riferimento il token specificato.|  
|[Metodo DeleteToken](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Elimina il token specificato dall'ambito dei metadati corrente.|  
|[Metodo GetSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Ottiene la dimensione stimata binaria dell'assembly nell'ambito corrente.|  
|[Metodo GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Ottiene un token per la firma dei metadati specificato.|  
|[Metodo GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Ottiene i metadati di un token per il tipo con la firma dei metadati specificato.|  
|[Metodo Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.|  
|[Metodo MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Unisce in corrente ambito tutti gli ambiti di metadati specificati da uno o più chiamate precedenti al `IMetaDataEmit::Merge`.|  
|[Metodo Save](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Salva tutti i metadati nell'ambito corrente del file all'indirizzo specificato.|  
|[Metodo SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Salva tutti i metadati nell'ambito corrente per l'area specificata di memoria.|  
|[Metodo SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Salva tutti i metadati nell'ambito corrente specificato `IStream`.|  
|[Metodo SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Imposta o aggiorna la firma di un tipo definito da una chiamata precedente al layout della classe `IMetaDataEmit::DefineTypeDef`.|  
|[Metodo SetCustomAttributeValue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Imposta o aggiorna il valore di un attributo personalizzato definito da una chiamata precedente a `IMetaDataEmit::DefineCustomAttribute`.|  
|[Metodo SetEventProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Imposta o aggiorna la funzionalità specificata di un evento definito da una chiamata precedente a `IMetaDataEmit::DefineEvent`.|  
|[Metodo SetFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Imposta i PInvoke informazioni di marshalling per il parametro di metodo viene restituito, campo o metodo fa riferimento il token specificato.|  
|[Metodo SetFieldProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Imposta o aggiorna il valore predefinito per il campo fa riferimento il token specificato.|  
|[Metodo SetFieldRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Imposta un valore della variabile globale per l'indirizzo virtuale relativo del campo a cui fa riferimento il token specificato.|  
|[Metodo SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Imposta il metodo specificato fa riferimento `IUnknown` puntatore come un callback di notifica per riassegnazioni di token.|  
|[Metodo SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Imposta o aggiorna la firma dei metadati dell'implementazione del metodo ereditato fa riferimento il token specificato.|  
|[Metodo SetMethodProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Imposta o aggiorna la funzionalità, archiviata in corrispondenza di indirizzo virtuale relativo specificato, di un metodo definito da una chiamata precedente a `IMetaDataEmit::DefineMethod`.|  
|[Metodo SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Aggiorna i riferimenti a un modulo definito da una chiamata precedente a `IMetaDataEmit::DefineModuleRef`.|  
|[Metodo SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Imposta o modifica le funzionalità di un parametro del metodo che è stato definito da una chiamata precedente a `IMetaDataEmit::DefineParam`.|  
|[Metodo SetParent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Stabilisce che il membro specificato, come definito da una chiamata precedente a `IMetaDataEmit::DefineMemberRef`, è un membro del tipo specificato, come definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef`.|  
|[Metodo SetPermissionSetProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Imposta o aggiorna le funzionalità della firma dei metadati di un set di autorizzazioni definito da una chiamata precedente a `IMetaDataEmit::DefinePermissionSet`.|  
|[Metodo SetPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Imposta o modifica le funzionalità di firma del metodo PInvoke, come definito da una chiamata precedente a `IMetaDataEmit::DefinePinvokeMap`.|  
|[Metodo SetPropertyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Imposta le funzioni archiviate nei metadati per una proprietà definita da una chiamata precedente a `IMetaDataEmit::DefineProperty`.|  
|[Metodo SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Imposta l'indirizzo virtuale relativo del metodo specificato.|  
|[Metodo SetTypeDefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Imposta le funzionalità di un tipo definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef`.|  
|[Metodo TranslateSigWithScope](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito unito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** Vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in Mscoree. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche
- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
