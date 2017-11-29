---
title: Interfaccia IMetaDataImport
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport
helpviewer_keywords: IMetaDataImport interface [.NET Framework metadata]
ms.assetid: 0adbbd35-5e8d-4fec-8268-dc70a07c5975
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6c7f1c7e99df61cc0cd33e1697de52a039d412df
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport-interface"></a>Interfaccia IMetaDataImport
Fornisce metodi per importare e modificare i metadati esistenti da un file eseguibile portabile (PE) o da un'altra origine, ad esempio una libreria dei tipi o un binario dei metadati di runtime autonomo.  
  
## <a name="methods"></a>Metodi  
  
|Metodo|Descrizione|  
|------------|-----------------|  
|[CloseEnum (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-closeenum-method.md)|Chiude l'enumeratore con l'handle specificato.|  
|[CountEnum (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-countenum-method.md)|Ottiene il numero di elementi nell'enumeratore con l'handle specificato.|  
|[EnumCustomAttributes (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumcustomattributes-method.md)|Enumera un elenco di token di definizione di attributo personalizzato associati al tipo o al membro specificato.|  
|[EnumEvents (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumevents-method.md)|Enumera i token di definizione di evento per il token TypeDef specificato.|  
|[EnumFields (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfields-method.md)|Enumera i token FieldDef per il tipo a cui fa riferimento il token TypeDef specificato.|  
|[EnumFieldsWithName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumfieldswithname-method.md)|Enumera i token FieldDef del tipo specificato con il nome specificato.|  
|[EnumInterfaceImpls (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enuminterfaceimpls-method.md)|Enumera i token MethodDef che rappresentano le implementazioni dell'interfaccia.|  
|[EnumMemberRefs (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummemberrefs-method.md)|Enumera i token MemberRef che rappresentano i membri del tipo specificato.|  
|[EnumMembers (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummembers-method.md)|Enumera i token MemberDef che rappresentano i membri del tipo specificato.|  
|[EnumMembersWithName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummemberswithname-method.md)|Enumera i token MemberDef che rappresentano i membri del tipo specificato con il nome specificato.|  
|[EnumMethodImpls (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodimpls-method.md)|Enumera i token MethodBody e MethodDeclaration che rappresentano i metodi del tipo specificato.|  
|[EnumMethods (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md)|Enumera i token MethodDef che rappresentano i metodi del tipo specificato.|  
|[EnumMethodSemantics (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodsemantics-method.md)|Enumera le proprietà e gli eventi di modifica delle proprietà a cui è correlato il metodo specificato.|  
|[EnumMethodsWithName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethodswithname-method.md)|Enumera i metodi che hanno il nome specificato e che sono definiti dal tipo a cui fa riferimento il token TypeDef specificato.|  
|[EnumModuleRefs (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummodulerefs-method.md)|Enumera i token ModuleRef che rappresentano i moduli importati.|  
|[EnumParams (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumparams-method.md)|Enumera i token ParamDef che rappresentano i parametri del metodo a cui fa riferimento il token MethodDef specificato.|  
|[EnumPermissionSets (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumpermissionsets-method.md)|Enumera le autorizzazioni per gli oggetti in un ambito dei metadati specificato.|  
|[EnumProperties (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumproperties-method.md)|Enumera i token PropertyDef che rappresentano le proprietà del tipo a cui fa riferimento il token TypeDef specificato.|  
|[EnumSignatures (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumsignatures-method.md)|Enumera i token Signature che rappresentano le firme autonome nell'ambito corrente.|  
|[EnumTypeDefs (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypedefs-method.md)|Enumera i token TypeDef che rappresentano tutti i tipi all'interno dell'ambito corrente.|  
|[EnumTypeRefs (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtyperefs-method.md)|Enumera i token TypeRef definiti nell'ambito dei metadati corrente.|  
|[EnumTypeSpecs (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumtypespecs-method.md)|Enumera i token TypeSpec definiti nell'ambito dei metadati corrente.|  
|[EnumUnresolvedMethods (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumunresolvedmethods-method.md)|Enumera i token MemberDef che rappresentano i metodi non risolti nell'ambito dei metadati corrente.|  
|[EnumUserStrings (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enumuserstrings-method.md)|Enumera i token String che rappresentano le stringhe specificate a livello di codice (hard-coded) nell'ambito dei metadati corrente.|  
|[FindField (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findfield-method.md)|Ottiene un token FieldDef per il campo membro del tipo specificato a cui corrispondono il nome e la firma dei metadati specificati.|  
|[FindMember (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmember-method.md)|Ottiene un puntatore al token MemberDef per il membro definito dal tipo indicato con il nome e la firma dei metadati specificati.|  
|[FindMemberRef (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmemberref-method.md)|Ottiene un puntatore al token MemberRef per il membro definito dal tipo indicato con il nome e la firma dei metadati specificati.|  
|[FindMethod (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findmethod-method.md)|Ottiene un puntatore al token MethodDef per il metodo definito dal tipo indicato con il nome e la firma dei metadati specificati.|  
|[FindTypeDefByName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findtypedefbyname-method.md)|Ottiene un puntatore al token TypeDef per il tipo con il nome specificato.|  
|[FindTypeRef (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-findtyperef-method.md)|Ottiene un puntatore al token di metadati TypeRef che fa riferimento al tipo con il nome specificato nell'ambito di ricerca indicato.|  
|[GetClassLayout (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md)|Ottiene le informazioni sul layout per la classe a cui fa riferimento il token TypeDef specificato.|  
|[GetCustomAttributeByName (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getcustomattributebyname-method.md)|Ottiene il valore dell'attributo personalizzato, dato il relativo nome.|  
|[GetCustomAttributeProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getcustomattributeprops-method.md)|Ottiene il valore dell'attributo personalizzato, dato il relativo token di metadati.|  
|[GetEventProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-geteventprops-method.md)|Ottiene informazioni sui metadati, tra cui il tipo dichiarante, i metodi di aggiunta ed eliminazione per i delegati, i flag e gli altri dati associati, per l'evento rappresentato dal token specificato.|  
|[GetFieldMarshal (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getfieldmarshal-method.md)|Ottiene un puntatore al tipo nativo non gestito del campo rappresentato dal token di metadati specificato.|  
|[GetFieldProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getfieldprops-method.md)|Ottiene i metadati associati al campo a cui fa riferimento il token FieldDef specificato.|  
|[Metodo GetInterfaceImplProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getinterfaceimplprops-method.md)|Ottiene un puntatore ai token di metadati per il tipo che implementa il metodo specificato e per l'interfaccia che dichiara tale metodo.|  
|[GetMemberProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmemberprops-method.md)|Ottiene le informazioni sui metadati, inclusi il nome, la firma binaria e l'indirizzo virtuale relativo, del membro del tipo a cui fa riferimento il token di metadati specificato.|  
|[GetMemberRefProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmemberrefprops-method.md)|Ottiene i metadati associati al membro a cui fa riferimento il token specificato.|  
|[Metodo GetMethodProps](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmethodprops-method.md)|Ottiene i metadati associati al metodo a cui fa riferimento il token MethodDef specificato.|  
|[GetMethodSemantics (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmethodsemantics-method.md)|Ottiene un puntatore alla relazione tra il metodo a cui fa riferimento il token MethodDef specificato e l'associazione di proprietà ed evento a cui fa riferimento il token EventProp specificato.|  
|[GetModuleFromScope (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmodulefromscope-method.md)|Ottiene un puntatore al token di metadati per il modulo a cui si fa riferimento nell'ambito dei metadati corrente.|  
|[GetModuleRefProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getmodulerefprops-method.md)|Ottiene il nome del modulo a cui fa riferimento il token di metadati specificato.|  
|[GetNameFromToken (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnamefromtoken-method.md)|Ottiene il nome in formato UTF-8 dell'oggetto a cui fa riferimento il token di metadati specificato.|  
|[GetNativeCallConvFromSig (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnativecallconvfromsig-method.md)|Ottiene la convenzione di chiamata nativa per il metodo rappresentato dal puntatore a firma specificato.|  
|[GetNestedClassProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getnestedclassprops-method.md)|Ottiene il token TypeDef per il tipo dell'elemento padre che contiene il tipo annidato specificato.|  
|[GetParamForMethodIndex (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getparamformethodindex-method.md)|Ottiene un puntatore al token che rappresenta il parametro nella posizione ordinale specificata nella sequenza di parametri di metodo relativi al metodo rappresentato dal token MethodDef specificato.|  
|[GetParamProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getparamprops-method.md)|Ottiene i valori di metadati relativi al parametro a cui fa riferimento il token ParamDef specificato.|  
|[GetPermissionSetProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpermissionsetprops-method.md)|Ottiene i metadati associati all'oggetto System.Security.PermissionSet rappresentato dal token Permission specificato.|  
|[GetPinvokeMap](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpinvokemap-method.md)|Ottiene un token ModuleRef per rappresentare l'assembly di destinazione di una chiamata PInvoke.|  
|[GetPropertyProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getpropertyprops-method.md)|Ottiene i metadati associati alla proprietà rappresentata dal token specificato.|  
|[GetRVA (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getrva-method.md)|Ottiene l'offset dell'indirizzo virtuale relativo dell'oggetto codice rappresentato dal token specificato.|  
|[GetScopeProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getscopeprops-method.md)|Ottiene il nome ed eventualmente l'identificatore di versione dell'assembly o del modulo nell'ambito dei metadati corrente.|  
|[GetSigFromToken (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getsigfromtoken-method.md)|Ottiene la firma binaria dei metadati associata al token specificato.|  
|[GetTypeDefProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettypedefprops-method.md)|Restituisce le informazioni sui metadati per il tipo rappresentato dal token TypeDef specificato.|  
|[GetTypeRefProps (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettyperefprops-method.md)|Ottiene i metadati associati al tipo a cui fa riferimento il token TypeRef specificato.|  
|[GetTypeSpecFromToken (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-gettypespecfromtoken-method.md)|Ottiene la firma binaria dei metadati della specifica del tipo rappresentata dal token indicato.|  
|[GetUserString (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getuserstring-method.md)|Ottiene la stringa letterale rappresentata dal token di metadati specificato.|  
|[IsGlobal (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-isglobal-method.md)|Ottiene un valore che indica se il campo, il metodo o il tipo rappresentato dal token di metadati specificato ha ambito globale.|  
|[IsValidToken (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-isvalidtoken-method.md)|Ottiene un valore che indica se il token specificato contiene un riferimento valido a un oggetto codice.|  
|[ResetEnum (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-resetenum-method.md)|Reimposta l'enumeratore specificato nella posizione specificata.|  
|[ResolveTypeRef (metodo)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-resolvetyperef-method.md)|Ottiene le informazioni per il tipo a cui fa riferimento il token TypeRef specificato.|  
  
## <a name="remarks"></a>Note  
 L'interfaccia `IMetaDataImport` è progettata principalmente per essere usata da strumenti e servizi che importeranno informazioni sul tipo, ad esempio strumenti di sviluppo, o gestiranno componenti distribuiti, quali servizi di risoluzione o attivazione. I metodi di `IMetaDataImport` rientrano nelle seguenti categorie di attività:  
  
-   Enumerazione di raccolte di elementi nell'ambito dei metadati.  
  
-   Ricerca di un elemento con una serie specifica di caratteristiche.  
  
-   Recupero delle proprietà di un elemento specificato.  
  
-   I metodi Get sono progettati specificamente per restituire le proprietà a valore singolo di un elemento dei metadati. Quando la proprietà è un riferimento a un altro elemento, viene restituito un token per tale elemento. Qualunque tipo di input del puntatore può essere NULL per indicare che il valore in questione non è richiesto. Per ottenere proprietà che siano essenzialmente oggetti Collection, ad esempio la raccolta di interfacce implementate da una classe, usare i metodi di enumerazione.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in MsCorEE.dll  
  
 **Versioni di .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfacce di metadati](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)  
 [IMetaDataImport2 (interfaccia)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
