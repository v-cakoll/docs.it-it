---
title: Uso di contratti dati
description: Informazioni su un contratto dati, che definisce, per ogni parametro o tipo restituito, i dati serializzati per essere scambiati tra un client e un server WCF.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataContractAttribute class
- WCF, data
- data contracts [WCF]
ms.assetid: a3ae7b21-c15c-4c05-abd8-f483bcbf31af
ms.openlocfilehash: 80ea2a8bd67c627fbe11ee07e640704c1a41ef7b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244725"
---
# <a name="using-data-contracts"></a>Uso di contratti dati
Un *contratto dati* è un accordo formale tra un servizio e un client che descrive astrattamente i dati da scambiare. Per comunicare, non è necessario che il client e il servizio condividano gli stessi tipi, ma solo gli stessi contratti dati. Un contratto dati definisce con precisione, per ogni parametro o tipo restituito, i dati serializzati (trasformati in XML) che verranno scambiati.  
  
## <a name="data-contract-basics"></a>Nozioni fondamentali dei contratti dati  
 Per impostazione predefinita, Windows Communication Foundation (WCF) utilizza un motore di serializzazione denominato serializzatore dei contratti dati per serializzare e deserializzare i dati, ovvero convertirli in e da XML. Tutti .NET Framework tipi primitivi, ad esempio numeri interi e stringhe, nonché alcuni tipi trattati come primitivi, ad esempio <xref:System.DateTime> e <xref:System.Xml.XmlElement> , possono essere serializzati senza altre preparazioni e vengono considerati come con contratti dati predefiniti. Molti tipi di .NET Framework hanno anche contratti dati esistenti. Per un elenco completo dei tipi serializzabili, vedere [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md).  
  
 Per poter essere serializzabili, è necessario che i nuovi tipi complessi creati dispongano di un contratto dati appositamente definito. Per impostazione predefinita, tramite <xref:System.Runtime.Serialization.DataContractSerializer> viene dedotto il contratto dati e vengono serializzati tutti i tipi visibili pubblicamente. Vengono serializzati i campi e le proprietà di lettura/scrittura pubblici del tipo. È possibile rifiutare esplicitamente i membri per la serializzazione tramite <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute>. È inoltre possibile creare in modo esplicito un contratto dati utilizzando gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> . Ciò viene di norma realizzato applicando l'attributo <xref:System.Runtime.Serialization.DataContractAttribute> al tipo. Questo attributo può essere applicato a classi, strutture ed enumerazioni. L'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> deve quindi essere applicato a ogni membro del tipo di contratto dati per indicare che si tratta di un *membro dati*, ovvero che deve essere serializzato. Per ulteriori informazioni, vedere [tipi serializzabili](serializable-types.md).  
  
### <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato un contratto di servizio (un'interfaccia) a cui sono stati applicati in modo esplicito gli attributi <xref:System.ServiceModel.ServiceContractAttribute> e <xref:System.ServiceModel.OperationContractAttribute> . Nell'esempio viene mostrato che i tipi primitivi non richiedono un contratto dati, diversamente da un tipo complesso.  
  
 [!code-csharp[C_DataContract#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#1)]
 [!code-vb[C_DataContract#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#1)]  
  
 Nell'esempio seguente viene illustrato come creare un contratto dati per il tipo `MyTypes.PurchaseOrder` creato applicando gli attributi <xref:System.Runtime.Serialization.DataContractAttribute> e <xref:System.Runtime.Serialization.DataMemberAttribute> alla classe e ai relativi membri.  
  
 [!code-csharp[C_DataContract#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#2)]
 [!code-vb[C_DataContract#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#2)]  
  
### <a name="notes"></a>Note  
 Nelle note seguenti sono contenuti gli elementi da tenere presenti durante la creazione di contratti dati:  
  
- L'attributo <xref:System.Runtime.Serialization.IgnoreDataMemberAttribute> viene accettato solo se utilizzato con tipi non contrassegnati. Sono inclusi i tipi non contrassegnati con uno degli attributi <xref:System.Runtime.Serialization.DataContractAttribute>, <xref:System.SerializableAttribute>, <xref:System.Runtime.Serialization.CollectionDataContractAttribute>o <xref:System.Runtime.Serialization.EnumMemberAttribute> oppure contrassegnati come serializzabili in qualsiasi altro modo (ad esempio <xref:System.Xml.Serialization.IXmlSerializable>).  
  
- È possibile applicare l'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> a campi e proprietà.  
  
- I livelli di accessibilità ai membri (interno, privato, protetto o pubblico) non influiscono in alcun modo sul contratto dati.  
  
- L'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> viene ignorato se applicato a membri statici.  
  
- Durante la serializzazione il codice della proprietà get viene chiamato per i membri dati della proprietà per ottenere il valore delle proprietà da serializzare.  
  
- Durante la deserializzazione viene prima creato un oggetto non inizializzato, senza chiamare alcun costruttore per il tipo, quindi vengono deserializzati tutti i membri dati.  
  
- Durante la deserializzazione il codice della proprietà set viene chiamato per i membri dati della proprietà per impostare le proprietà sul valore in fase di deserializzazione.  
  
- Perché un contratto dati sia valido, deve essere possibile serializzare tutti i relativi membri dati. Per un elenco completo dei tipi serializzabili, vedere [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md).  
  
     I tipi generici sono gestiti esattamente nello stesso modo dei tipi non generici. Non vi sono requisiti speciali per i parametri generici. Si consideri ad esempio il tipo seguente:  
  
 [!code-csharp[C_DataContract#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#3)]
 [!code-vb[C_DataContract#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#3)]  
  
 Il tipo è serializzabile indipendentemente dal fatto che il tipo utilizzato per il parametro di tipo generico (`T`) sia serializzabile o meno. Poiché deve essere possibile serializzare tutti i membri dati, il tipo seguente è serializzabile solo se il parametro di tipo generico è anch'esso serializzabile, come indicato nel codice seguente.  
  
 [!code-csharp[C_DataContract#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_datacontract/cs/source.cs#4)]
 [!code-vb[C_DataContract#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_datacontract/vb/source.vb#4)]  
  
 Per un esempio di codice completo di un servizio WCF che definisce un contratto dati, vedere l'esempio [Basic Data Contract](../samples/basic-data-contract.md) .  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataMemberAttribute>
- <xref:System.Runtime.Serialization.DataContractAttribute>
- [Tipi serializzabili](serializable-types.md)
- [Nomi di contratto dati](data-contract-names.md)
- [Data Contract Equivalence](data-contract-equivalence.md)
- [Ordine dei membri dati](data-member-order.md)
- [Tipi conosciuti di contratto dati](data-contract-known-types.md)
- [Contratti dati compatibili con le versioni successive](forward-compatible-data-contracts.md)
- [Controllo delle versioni dei contratti dati](data-contract-versioning.md)
- [Callback di serializzazione a tolleranza di versione](version-tolerant-serialization-callbacks.md)
- [Valori predefiniti dei membri dati](data-member-default-values.md)
- [Types Supported by the Data Contract Serializer](types-supported-by-the-data-contract-serializer.md)
- [Procedura: creare un contratto dati di base per una classe o una struttura](how-to-create-a-basic-data-contract-for-a-class-or-structure.md)
