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
ms.openlocfilehash: a2c2512abc28f0140fc261c5136c7e1255db96de
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/27/2020
ms.locfileid: "84009212"
---
# <a name="imetadataemit-interface"></a>Interfaccia IMetaDataEmit
Fornisce metodi per creare, modificare e salvare i metadati relativi all'assembly nell'ambito attualmente definito. I metadati possono essere archiviati in memoria o salvati su disco.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[Metodo ApplyEditAndContinue](imetadataemit-applyeditandcontinue-method.md)|Aggiorna l'ambito dell'assembly corrente con le modifiche apportate nell'oggetto specificato `pImport` .|  
|[Metodo DefineCustomAttribute](imetadataemit-definecustomattribute-method.md)|Crea una definizione per un attributo personalizzato con la firma dei metadati specificata, da allegare all'oggetto specificato e ottiene un token per la definizione di attributo personalizzato.|  
|[Metodo DefineEvent](imetadataemit-defineevent-method.md)|Crea una definizione per un evento con la firma dei metadati specificata e ottiene un token per la definizione dell'evento.|  
|[Metodo DefineField](imetadataemit-definefield-method.md)|Crea una definizione per un campo con la firma dei metadati specificata e ottiene un token per la definizione del campo.|  
|[Metodo DefineImportMember](imetadataemit-defineimportmember-method.md)|Crea una definizione per un membro di un tipo definito in un modulo esterno all'ambito corrente e ottiene un token per la definizione di riferimento.|  
|[Metodo DefineImportType](imetadataemit-defineimporttype-method.md)|Crea una definizione per un riferimento a un tipo definito in un modulo esterno all'ambito corrente e ottiene un token per la definizione di riferimento.|  
|[Metodo DefineMemberRef](imetadataemit-definememberref-method.md)|Crea una definizione per un riferimento a un membro di un modulo esterno all'ambito corrente e ottiene un token per la definizione di riferimento.|  
|[Metodo DefineMethod](imetadataemit-definemethod-method.md)|Crea una definizione per un metodo con la firma specificata e restituisce un token a tale definizione di metodo.|  
|[Metodo DefineMethodImpl](imetadataemit-definemethodimpl-method.md)|Crea una definizione per l'implementazione di un metodo ereditato da un'interfaccia e restituisce un token a tale definizione di implementazione del metodo.|  
|[Metodo DefineModuleRef](imetadataemit-definemoduleref-method.md)|Crea la firma dei metadati per un modulo con il nome specificato.|  
|[Metodo DefineNestedType](imetadataemit-definenestedtype-method.md)|Crea la firma dei metadati di una definizione di tipo e restituisce un `mdTypeDef` token per quel tipo, specificando inoltre che il tipo definito è un membro del tipo a cui fa riferimento `tdEncloser` .|  
|[Metodo DefineParam](imetadataemit-defineparam-method.md)|Crea una definizione di parametro con la firma specificata per il metodo a cui fa riferimento il token specificato e ottiene un token per la definizione del parametro.|  
|[Metodo DefinePermissionSet](imetadataemit-definepermissionset-method.md)|Crea una definizione per un set di autorizzazioni con la firma dei metadati specificata e ottiene un token per la definizione del set di autorizzazioni.|  
|[Metodo DefinePinvokeMap](imetadataemit-definepinvokemap-method.md)|Imposta le funzionalità della firma PInvoke del metodo a cui fa riferimento il token specificato.|  
|[Metodo DefineProperty](imetadataemit-defineproperty-method.md)|Crea una definizione di proprietà per il tipo specificato, con le `get` funzioni di accesso ai metodi e specificate `set` , e ottiene un token per la definizione della proprietà.|  
|[Metodo DefineSecurityAttributeSet](imetadataemit-definesecurityattributeset-method.md)|Crea un set di autorizzazioni di sicurezza per la connessione all'oggetto a cui fa riferimento il token specificato.|  
|[Metodo DefineTypeDef](imetadataemit-definetypedef-method.md)|Crea una definizione di tipo per un tipo di Common Language Runtime e ottiene un token di metadati per la definizione del tipo.|  
|[Metodo DefineTypeRefByName](imetadataemit-definetyperefbyname-method.md)|Ottiene un token di metadati per un tipo definito in un altro modulo al di fuori dell'ambito corrente.|  
|[Metodo DefineUserString](imetadataemit-defineuserstring-method.md)|Ottiene un token di metadati per la stringa letterale specificata.|  
|[Metodo DeleteClassLayout](imetadataemit-deleteclasslayout-method.md)|Elimina definitivamente la firma dei metadati del layout della classe per il tipo a cui fa riferimento il token specificato.|  
|[Metodo DeleteFieldMarshal](imetadataemit-deletefieldmarshal-method.md)|Elimina la firma dei metadati di marshalling PInvoke per l'oggetto a cui fa riferimento il token specificato.|  
|[Metodo DeletePinvokeMap](imetadataemit-deletepinvokemap-method.md)|Elimina i metadati di mapping PInvoke per l'oggetto a cui fa riferimento il token specificato.|  
|[Metodo DeleteToken](imetadataemit-deletetoken-method.md)|Elimina il token specificato dall'ambito dei metadati corrente.|  
|[Metodo GetSaveSize](imetadataemit-getsavesize-method.md)|Ottiene la dimensione binaria stimata dell'assembly nell'ambito corrente.|  
|[Metodo GetTokenFromSig](imetadataemit-gettokenfromsig-method.md)|Ottiene un token per la firma dei metadati specificata.|  
|[Metodo GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md)|Ottiene un token di metadati per il tipo con la firma dei metadati specificata.|  
|[Metodo Merge](imetadataemit-merge-method.md)|Aggiunge l'ambito importato specificato all'elenco di ambiti da unire.|  
|[Metodo MergeEnd](imetadataemit-mergeend-method.md)|Esegue il merge nell'ambito corrente di tutti gli ambiti dei metadati specificati da una o più chiamate precedenti a `IMetaDataEmit::Merge` .|  
|[Metodo Save](imetadataemit-save-method.md)|Salva tutti i metadati nell'ambito corrente nel file in corrispondenza dell'indirizzo specificato.|  
|[Metodo SaveToMemory](imetadataemit-savetomemory-method.md)|Salva tutti i metadati nell'ambito corrente nell'area di memoria specificata.|  
|[Metodo SaveToStream](imetadataemit-savetostream-method.md)|Salva tutti i metadati nell'ambito corrente nell'oggetto specificato `IStream` .|  
|[Metodo SetClassLayout](imetadataemit-setclasslayout-method.md)|Imposta o aggiorna la firma del layout della classe di un tipo definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef` .|  
|[Metodo SetCustomAttributeValue](imetadataemit-setcustomattributevalue-method.md)|Imposta o aggiorna il valore di un attributo personalizzato definito da una chiamata precedente a `IMetaDataEmit::DefineCustomAttribute` .|  
|[Metodo SetEventProps](imetadataemit-seteventprops-method.md)|Imposta o aggiorna la funzionalità specificata di un evento definito da una chiamata precedente a `IMetaDataEmit::DefineEvent` .|  
|[Metodo SetFieldMarshal](imetadataemit-setfieldmarshal-method.md)|Imposta le informazioni di marshalling PInvoke per il campo, il ritorno del metodo o il parametro del metodo a cui fa riferimento il token specificato.|  
|[Metodo SetFieldProps](imetadataemit-setfieldprops-method.md)|Imposta o aggiorna il valore predefinito per il campo a cui fa riferimento il token di campo specificato.|  
|[Metodo SetFieldRVA](imetadataemit-setfieldrva-method.md)|Imposta un valore di variabile globale per l'indirizzo virtuale relativo del campo a cui fa riferimento il token specificato.|  
|[Metodo SetHandler](imetadataemit-sethandler-method.md)|Imposta il metodo a cui fa riferimento il `IUnknown` puntatore specificato come callback di notifica per i mapping del token.|  
|[Metodo SetMethodImplFlags](imetadataemit-setmethodimplflags-method.md)|Imposta o aggiorna la firma dei metadati dell'implementazione del metodo ereditato a cui fa riferimento il token specificato.|  
|[Metodo SetMethodProps](imetadataemit-setmethodprops-method.md)|Imposta o aggiorna la funzionalità, archiviata in corrispondenza dell'indirizzo virtuale relativo specificato, di un metodo definito da una chiamata precedente a `IMetaDataEmit::DefineMethod` .|  
|[Metodo SetModuleProps](imetadataemit-setmoduleprops-method.md)|Aggiorna i riferimenti a un modulo definito da una chiamata precedente a `IMetaDataEmit::DefineModuleRef` .|  
|[Metodo SetParamProps](imetadataemit-setparamprops-method.md)|Imposta o modifica le funzionalità di un parametro del metodo definito da una chiamata precedente a `IMetaDataEmit::DefineParam` .|  
|[Metodo SetParent](imetadataemit-setparent-method.md)|Stabilisce che il membro specificato, in base a quanto definito da una chiamata precedente a `IMetaDataEmit::DefineMemberRef` , è un membro del tipo specificato, in base a quanto definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef` .|  
|[Metodo SetPermissionSetProps](imetadataemit-setpermissionsetprops-method.md)|Imposta o aggiorna le funzionalità della firma dei metadati di un set di autorizzazioni definito da una chiamata precedente a `IMetaDataEmit::DefinePermissionSet` .|  
|[Metodo SetPinvokeMap](imetadataemit-setpinvokemap-method.md)|Imposta o modifica le funzionalità della firma PInvoke di un metodo, come definito da una chiamata precedente a `IMetaDataEmit::DefinePinvokeMap` .|  
|[Metodo SetPropertyProps](imetadataemit-setpropertyprops-method.md)|Imposta le funzionalità archiviate nei metadati per una proprietà definita da una chiamata precedente a `IMetaDataEmit::DefineProperty` .|  
|[Metodo SetRVA](imetadataemit-setrva-method.md)|Imposta l'indirizzo virtuale relativo del metodo specificato.|  
|[Metodo SetTypeDefProps](imetadataemit-settypedefprops-method.md)|Imposta le funzionalità di un tipo definito da una chiamata precedente a `IMetaDataEmit::DefineTypeDef` .|  
|[Metodo TranslateSigWithScope](imetadataemit-translatesigwithscope-method.md)|Importa un assembly nell'ambito corrente e ottiene una nuova firma dei metadati per l'ambito Unito.|  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [Requisiti di sistema di .NET Framework](../../get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** Usato come risorsa in MsCorEE. dll  
  
 **Versioni .NET Framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Interfacce di metadati](metadata-interfaces.md)
- [Interfaccia IMetaDataEmit2](imetadataemit2-interface.md)
