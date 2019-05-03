---
title: Tipi supportati dal serializzatore dei contratti dati
ms.date: 03/30/2017
helpviewer_keywords:
- serialization [WCF], supported types
ms.assetid: 7381b200-437a-4506-9556-d77bf1bc3f34
ms.openlocfilehash: 9c532858ba3b93d427e5c0455f953db2499ebd6a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61918879"
---
# <a name="types-supported-by-the-data-contract-serializer"></a>Tipi supportati dal serializzatore dei contratti dati
Windows Communication Foundation (WCF) viene utilizzato il <xref:System.Runtime.Serialization.DataContractSerializer> come motore di serializzazione predefinito per convertire i dati in XML e per convertire XML in dati. <xref:System.Runtime.Serialization.DataContractSerializer> è progettato per serializzare tipi di *contratto dati* . Supporta tuttavia molti altri tipi che possono essere considerati come tipi dotati di un contratto dati implicito. Nell'elenco seguente sono riportati tutti i tipi serializzabili:  
  
- Tutti i tipi visibili pubblicamente con un costruttore che non dispone di parametri.  
  
- Tipi di contratto dati. Questi sono i tipi ai quali è stato applicato l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> . I nuovi tipi personalizzati che rappresentano oggetti business devono in genere essere creati come tipi di contratto dati. Per altre informazioni, vedere [Using Data Contracts](../../../../docs/framework/wcf/feature-details/using-data-contracts.md) e [tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md).  
  
- Tipi di raccolta. Questi sono i tipi che rappresentano elenchi di dati. Possono essere matrici normali di tipi, o tipi di raccolta, ad esempio <xref:System.Collections.ArrayList> e <xref:System.Collections.Generic.Dictionary%602>. L'attributo <xref:System.Runtime.Serialization.CollectionDataContractAttribute> può essere utilizzato per personalizzare la serializzazione di questi tipi, ma non è obbligatorio. Per altre informazioni, vedere [tipi di raccolta nei contratti dati](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md).  
  
- Tipi di enumerazione. Le enumerazioni, incluse quelle di flag, sono serializzabili. Facoltativamente, i tipi di enumerazione possono essere contrassegnati con l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> , nel qual caso ogni membro che partecipa alla serializzazione deve essere contrassegnato con l'attributo <xref:System.Runtime.Serialization.EnumMemberAttribute> . I membri non contrassegnati non vengono serializzati. Per altre informazioni, vedere [tipi di enumerazioni nei contratti dati](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md).  
  
- Tipi primitivi di .NET Framework. I tipi seguenti incorporati in .NET Framework possono essere tutti serializzati e sono considerati tipi primitivi: <xref:System.Byte>, <xref:System.SByte>, <xref:System.Int16>, <xref:System.Int32>, <xref:System.Int64>, <xref:System.UInt16>, <xref:System.UInt32>, <xref:System.UInt64>, <xref:System.Single>, <xref:System.Double>, <xref:System.Boolean>, <xref:System.Char>, <xref:System.Decimal>, <xref:System.Object>e <xref:System.String>.  
  
- Altri tipi primitivi. Questi tipi non sono primitivi in .NET Framework, ma sono trattati come primitivi nel formato XML serializzato. Questi tipi sono <xref:System.DateTime>, <xref:System.DateTimeOffset>, <xref:System.TimeSpan>, <xref:System.Guid>, <xref:System.Uri>, <xref:System.Xml.XmlQualifiedName>e matrici di <xref:System.Byte>.  
  
    > [!NOTE]
    >  Contrariamente ad altri tipi primitivi, <xref:System.DateTimeOffset> non è un tipo conosciuto per impostazione predefinita. Per altre informazioni, vedere [Data Contract Known Types](../../../../docs/framework/wcf/feature-details/data-contract-known-types.md)).  
  
- Tipi contrassegnati con l'attributo <xref:System.SerializableAttribute> . Numerosi tipi inclusi nella libreria della classe di base [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] rientrano in questa categoria. <xref:System.Runtime.Serialization.DataContractSerializer> supporta completamente questo modello di programmazione della serializzazione utilizzato da .NET Framework Remoting, <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter>e <xref:System.Runtime.Serialization.Formatters.Soap.SoapFormatter>, compreso il supporto per l'interfaccia <xref:System.Runtime.Serialization.ISerializable> .  
  
- Tipi che rappresentano XML non elaborato o tipi che rappresentano dati relazionali [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)] . <xref:System.Xml.XmlElement> e la matrice di tipi <xref:System.Xml.XmlNode> sono supportati come un modo di rappresentazione diretta di XML. Sono inoltre supportati i tipi che implementano l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> , compreso l'attributo <xref:System.Xml.Serialization.XmlSchemaProviderAttribute> correlato e i tipi <xref:System.Xml.Linq.XDocument> e <xref:System.Xml.Linq.XElement> . L'attributo [!INCLUDE[vstecado](../../../../includes/vstecado-md.md)]<xref:System.Data.DataTable> e il tipo <xref:System.Data.DataSet> (come le sue classi derivate tipizzate) implementano tutti l'interfaccia <xref:System.Xml.Serialization.IXmlSerializable> e di conseguenza appartengono a questa categoria. Per altre informazioni, vedere [tipi XML e ADO.NET nei contratti dati](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md).  
  
## <a name="limitations-of-using-certain-types-in-partial-trust-mode"></a>Limitazioni dell'utilizzo di certi tipi in modalità parzialmente attendibile  
 Nell'elenco seguente sono riportate le limitazioni relative all'utilizzo di determinati tipi in scenari in modalità parzialmente attendibile:  
  
- Per serializzare o deserializzare un tipo che implementa <xref:System.Runtime.Serialization.ISerializable> in codice parzialmente attendibile tramite <xref:System.Runtime.Serialization.DataContractSerializer> è necessario disporre delle autorizzazioni <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> e <xref:System.Security.Permissions.SecurityPermissionAttribute.UnmanagedCode%2A> .  
  
- Quando il codice WCF in esecuzione in [attendibilità parziale](../../../../docs/framework/wcf/feature-details/partial-trust.md) modalità, la serializzazione e deserializzazione dei `readonly` campi (entrambi `public` e `private`) non è supportato. Ciò è dovuto al fatto che IL generato non è verificabile e pertanto richiede autorizzazioni elevate.  
  
- Entrambe le classi <xref:System.Runtime.Serialization.DataContractSerializer> e <xref:System.Xml.Serialization.XmlSerializer> sono supportate in un ambiente di trust parziale. Tuttavia, l'utilizzo di <xref:System.Runtime.Serialization.DataContractSerializer> è soggetto alle condizioni seguenti:  
  
    - Tutti i tipi `[DataContract]` serializzabili devono essere pubblici.  
  
    - Tutti i campi `[DataMember]` o le proprietà in un tipo `[DataContract]` devono essere pubblici e di lettura/scrittura. La serializzazione e deserializzazione di `readonly` campi non è supportato durante l'esecuzione di WCF in un'applicazione parzialmente attendibile.  
  
    - L'attributo `[Serializable]`/`ISerializable]` non è supportato in un ambiente parzialmente attendibile.  
  
    - I tipi noti devono essere specificati nel codice o nella configurazione a livello di computer (`Machine.config`). I tipi noti non possono essere specificati nella configurazione a livello di applicazione per motivi di sicurezza.  
  
- I tipi che implementano <xref:System.Runtime.Serialization.IObjectReference> generano un'eccezione in un ambiente parzialmente attendibile, poiché il metodo <xref:System.Runtime.Serialization.IObjectReference.GetRealObject%2A> richiede l'autorizzazione di sicurezza `[SecurityPermission(SecurityAction.LinkDemand, Flags=SecurityPermissionFlag.SerializationFormatter)]`.  
  
## <a name="additional-notes-on-serialization"></a>Note aggiuntive sulla serializzazione  
 Le regole seguenti si applicano anche ai tipi supportati dal serializzatore di contratti dati:  
  
- I tipi generici sono totalmente supportati dal serializzatore dei contratti dati  
  
- I tipi nullable sono totalmente supportati dal serializzatore dei contratti dati  
  
- I tipi di interfaccia vengono trattati come <xref:System.Object> o, nel caso di interfacce di raccolta, come tipi di raccolta.  
  
- Sono supportate sia le strutture che le classi.  
  
- <xref:System.Runtime.Serialization.DataContractSerializer> non supporta il modello di programmazione utilizzato dai servizi Web <xref:System.Xml.Serialization.XmlSerializer> e [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] . In particolare, non supporta attributi quali <xref:System.Xml.Serialization.XmlElementAttribute> e <xref:System.Xml.Serialization.XmlAttributeAttribute>. Per abilitare il supporto per questo modello di programmazione, WCF deve essere impostato per utilizzare il <xref:System.Xml.Serialization.XmlSerializer> anziché il <xref:System.Runtime.Serialization.DataContractSerializer>.  
  
- Il tipo <xref:System.DBNull> viene trattato in modo speciale. È un tipo singleton e sulla deserializzazione il deserializzatore rispetta il vincolo singleton e punta tutti i riferimenti `DBNull` all'istanza singleton. Dato che `DBNull` è un tipo serializzabile, richiede l'autorizzazione <xref:System.Security.Permissions.SecurityPermissionAttribute.SerializationFormatter%2A> .  
  
## <a name="see-also"></a>Vedere anche

- [Tipi XML e ADO.NET nei contratti di dati](../../../../docs/framework/wcf/feature-details/xml-and-ado-net-types-in-data-contracts.md)
- [Uso di contratti di dati](../../../../docs/framework/wcf/feature-details/using-data-contracts.md)
- [Tipi serializzabili](../../../../docs/framework/wcf/feature-details/serializable-types.md)
- [Tipi di raccolta nei contratti di dati](../../../../docs/framework/wcf/feature-details/collection-types-in-data-contracts.md)
- [Tipi di enumerazione nei contratti di dati](../../../../docs/framework/wcf/feature-details/enumeration-types-in-data-contracts.md)
