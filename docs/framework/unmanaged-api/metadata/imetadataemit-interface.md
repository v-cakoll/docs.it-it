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
ms.openlocfilehash: b4ae599a0e5cdb604fd9a610728671b39c67af31
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/23/2019
ms.locfileid: "74440890"
---
# <a name="imetadataemit-interface"></a>Interfaccia IMetaDataEmit
Fornisce metodi per creare, modificare e salvare i metadati relativi all'assembly nell'ambito attualmente definito. I metadati possono essere archiviati in memoria o salvati su disco.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ApplyEditAndContinue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-applyeditandcontinue-method.md)|Aggiorna l'ambito dell'assembly corrente con le modifiche apportate all'`pImport`specificato.|  
|[Metodo DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md)|Crea una definizione per un attributo personalizzato con la firma dei metadati specificata, da allegare all'oggetto specificato e ottiene un token per la definizione di attributo personalizzato.|  
|[Metodo DefineEvent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineevent-method.md)|Crea una definizione per un evento con la firma dei metadati specificata e ottiene un token per la definizione dell'evento.|  
|[Metodo DefineField](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definefield-method.md)|Crea una definizione per un campo con la firma dei metadati specificata e ottiene un token per la definizione del campo.|  
|[Metodo DefineImportMember](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimportmember-method.md)|Crea una definizione per un membro di un tipo definito in un modulo esterno all'ambito corrente e ottiene un token per la definizione di riferimento.|  
|[Metodo DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)|Crea una definizione per un riferimento a un tipo definito in un modulo esterno all'ambito corrente e ottiene un token per la definizione di riferimento.|  
|[Metodo DefineMemberRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definememberref-method.md)|Crea una definizione per un riferimento a un membro di un modulo esterno all'ambito corrente e ottiene un token per la definizione di riferimento.|  
|[Metodo DefineMethod](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethod-method.md)|Crea una definizione per un metodo con la firma specificata e restituisce un token a tale definizione di metodo.|  
|[Metodo DefineMethodImpl](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemethodimpl-method.md)|Crea una definizione per l'implementazione di un metodo ereditato da un'interfaccia e restituisce un token a tale definizione di implementazione del metodo.|  
|[Metodo DefineModuleRef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definemoduleref-method.md)|Crea la firma dei metadati per un modulo con il nome specificato.|  
|[Metodo DefineNestedType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definenestedtype-method.md)|Crea la firma dei metadati di una definizione di tipo e restituisce un token di `mdTypeDef` per quel tipo, specificando anche che il tipo definito è un membro del tipo a cui viene fatto riferimento da `tdEncloser`.|  
|[Metodo DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)|Crea una definizione di parametro con la firma specificata per il metodo a cui fa riferimento il token specificato e ottiene un token per la definizione del parametro.|  
|[Metodo DefinePermissionSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepermissionset-method.md)|Crea una definizione per un set di autorizzazioni con la firma dei metadati specificata e ottiene un token per la definizione del set di autorizzazioni.|  
|[Metodo DefinePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definepinvokemap-method.md)|Imposta le funzionalità della firma PInvoke del metodo a cui fa riferimento il token specificato.|  
|[Metodo DefineProperty](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineproperty-method.md)|Crea una definizione di proprietà per il tipo specificato, con le funzioni di accesso `get` e `set` del metodo specificate e ottiene un token per la definizione della proprietà.|  
|[Metodo DefineSecurityAttributeSet](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definesecurityattributeset-method.md)|Crea un set di autorizzazioni di sicurezza per la connessione all'oggetto a cui fa riferimento il token specificato.|  
|[Metodo DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)|Crea una definizione di tipo per un tipo di Common Language Runtime e ottiene un token di metadati per la definizione del tipo.|  
|[Metodo DefineTypeRefByName](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetyperefbyname-method.md)|Ottiene un token di metadati per un tipo definito in un altro modulo al di fuori dell'ambito corrente.|  
|[Metodo DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md)|Ottiene un token di metadati per la stringa letterale specificata.|  
|[Metodo DeleteClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deleteclasslayout-method.md)|Elimina definitivamente la firma dei metadati del layout della classe per il tipo a cui fa riferimento il token specificato.|  
|[Metodo DeleteFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletefieldmarshal-method.md)|Elimina la firma dei metadati di marshalling PInvoke per l'oggetto a cui fa riferimento il token specificato.|  
|[Metodo DeletePinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletepinvokemap-method.md)|Elimina i metadati di mapping PInvoke per l'oggetto a cui fa riferimento il token specificato.|  
|[Metodo DeleteToken](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-deletetoken-method.md)|Elimina il token specificato dall'ambito dei metadati corrente.|  
|[Metodo GetSaveSize](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-getsavesize-method.md)|Ottiene la dimensione binaria stimata dell'assembly nell'ambito corrente.|  
|[Metodo GetTokenFromSig](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromsig-method.md)|Ottiene un token per la firma dei metadati specificata.|  
|[Metodo GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md)|Ottiene un token di metadati per il tipo con la firma dei metadati specificata.|  
|[Metodo Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md)|Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.|  
|[Metodo MergeEnd](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-mergeend-method.md)|Esegue il merge nell'ambito corrente di tutti gli ambiti dei metadati specificati da una o più chiamate precedenti a `IMetaDataEmit::Merge`.|  
|[Metodo Save](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-save-method.md)|Salva tutti i metadati nell'ambito corrente nel file in corrispondenza dell'indirizzo specificato.|  
|[Metodo SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md)|Salva tutti i metadati nell'ambito corrente nell'area di memoria specificata.|  
|[Metodo SaveToStream](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetostream-method.md)|Salva tutti i metadati nell'ambito corrente nel `IStream`specificato.|  
|[Metodo SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md)|Imposta o aggiorna la firma del layout della classe di un tipo definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef`.|  
|[Metodo SetCustomAttributeValue](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setcustomattributevalue-method.md)|Imposta o aggiorna il valore di un attributo personalizzato definito da una chiamata precedente a `IMetaDataEmit::DefineCustomAttribute`.|  
|[Metodo SetEventProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-seteventprops-method.md)|Imposta o aggiorna la funzionalità specificata di un evento definito da una chiamata precedente a `IMetaDataEmit::DefineEvent`.|  
|[Metodo SetFieldMarshal](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldmarshal-method.md)|Imposta le informazioni di marshalling PInvoke per il campo, il ritorno del metodo o il parametro del metodo a cui fa riferimento il token specificato.|  
|[Metodo SetFieldProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldprops-method.md)|Imposta o aggiorna il valore predefinito per il campo a cui fa riferimento il token di campo specificato.|  
|[Metodo SetFieldRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setfieldrva-method.md)|Imposta un valore di variabile globale per l'indirizzo virtuale relativo del campo a cui fa riferimento il token specificato.|  
|[Metodo SetHandler](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-sethandler-method.md)|Imposta il metodo a cui fa riferimento il puntatore `IUnknown` specificato come callback di notifica per le rimappe dei token.|  
|[Metodo SetMethodImplFlags](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodimplflags-method.md)|Imposta o aggiorna la firma dei metadati dell'implementazione del metodo ereditato a cui fa riferimento il token specificato.|  
|[Metodo SetMethodProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmethodprops-method.md)|Imposta o aggiorna la funzionalità, archiviata in corrispondenza dell'indirizzo virtuale relativo specificato, di un metodo definito da una chiamata precedente a `IMetaDataEmit::DefineMethod`.|  
|[Metodo SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md)|Aggiorna i riferimenti a un modulo definito da una chiamata precedente a `IMetaDataEmit::DefineModuleRef`.|  
|[Metodo SetParamProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparamprops-method.md)|Imposta o modifica le funzionalità di un parametro del metodo definito da una chiamata precedente a `IMetaDataEmit::DefineParam`.|  
|[Metodo SetParent](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setparent-method.md)|Stabilisce che il membro specificato, in base a quanto definito da una chiamata precedente a `IMetaDataEmit::DefineMemberRef`, è un membro del tipo specificato, in base a quanto definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef`.|  
|[Metodo SetPermissionSetProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpermissionsetprops-method.md)|Imposta o aggiorna le funzionalità della firma dei metadati di un set di autorizzazioni definito da una chiamata precedente a `IMetaDataEmit::DefinePermissionSet`.|  
|[Metodo SetPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpinvokemap-method.md)|Imposta o modifica le funzionalità della firma PInvoke di un metodo, come definito da una chiamata precedente a `IMetaDataEmit::DefinePinvokeMap`.|  
|[Metodo SetPropertyProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setpropertyprops-method.md)|Imposta le funzionalità archiviate nei metadati per una proprietà definita da una chiamata precedente a `IMetaDataEmit::DefineProperty`.|  
|[Metodo SetRVA](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setrva-method.md)|Imposta l'indirizzo virtuale relativo del metodo specificato.|  
|[Metodo SetTypeDefProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-settypedefprops-method.md)|Imposta le funzionalità di un tipo definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef`.|  
|[Metodo TranslateSigWithScope](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-translatesigwithscope-method.md)|Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito Unito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni di .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [Interfaccia IMetaDataEmit2](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
