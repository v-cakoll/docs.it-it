---
title: Valori predefiniti dei membri dati
description: Informazioni su come omettere un membro dati dai dati serializzati quando dispone di un .NET Framework valore predefinito. WCF può migliorare le prestazioni senza serializzare un valore predefinito.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data members [WCF], default values
- data members [WCF]
ms.assetid: 53a3b505-4b27-444b-b079-0eb84a97cfd8
ms.openlocfilehash: 97946a6b7da14efdcb5229b4cc5d0799eb8d7723
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247377"
---
# <a name="data-member-default-values"></a>Valori predefiniti dei membri dati
Nella .NET Framework i tipi hanno un concetto di *valori predefiniti*. Ad esempio, per i tipi di riferimento il valore predefinito è `null` mentre per un tipo Integer è zero. Talvolta, quando un membro dati è impostato sul relativo valore predefinito, conviene ometterlo dai dati serializzati. Infatti, poiché il membro ha un valore predefinito, non occorre serializzare un valore effettivo. Ciò risulta vantaggioso in termini di prestazioni.  
  
 Per omettere un membro dai dati serializzati, impostare la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> dell'attributo <xref:System.Runtime.Serialization.DataMemberAttribute> su `false`. L'impostazione predefinita è `true`.  
  
> [!NOTE]
> È consigliabile impostare la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> su `false` se esiste un'esigenza specifica da soddisfare, ad esempio fornire interoperabilità o ridurre le dimensioni dei dati.  
  
## <a name="example"></a>Esempio  
 Il codice seguente illustra vari membri in cui la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> è impostata su `false`.  
  
 [!code-csharp[DataMemberAttribute#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/datamemberattribute/cs/overview.cs#4)]
 [!code-vb[DataMemberAttribute#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/datamemberattribute/vb/overview.vb#4)]  
  
 Se si serializza un'istanza di questa classe, si verifica quanto segue: `employeeName` e `employeeID` vengono serializzati. Il valore null di `employeeName` e il valore zero di `employeeID` appartengono esplicitamente ai dati serializzati. Tuttavia, i membri `position`, `salary` e `bonus` non verranno serializzati. Infine, `targetSalary` viene serializzato normalmente, anche se la relativa proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> è impostata su `false`. Infatti, 57800 non corrisponde al valore predefinito .NET per un numero intero, ovvero zero.  
  
### <a name="xml-representation"></a>Rappresentazione XML  
 Se l'esempio precedente viene serializzato in XML, la rappresentazione risulta simile al codice seguente.  
  
```xml  
<Employee>  
   <employeeName xsi:nil="true" />  
   <employeeID>0</employeeID>  
<targetSalary>57800</targetSalary>  
</Employee>  
```  
  
 L'attributo `xsi:nil` è un attributo speciale dello spazio dei nomi delle istanze dell'XML Schema del W3C (World Wide Web Consortium) che fornisce un modo interoperativo per rappresentare in modo esplicito un valore nullo. Si noti che il codice XML non contiene alcuna informazione sui membri dati "position", "salary" e "bonus". Il destinatario può interpretare questa assenza di dati come possibilità di impostare tali membri rispettivamente come `null`, zero e `null`. Non esiste alcuna garanzia che un deserializzatore di terze parti esegua correttamente l'impostazione dei valori. È per questo motivo che è consigliabile evitare di utilizzare questo modello. La classe <xref:System.Runtime.Serialization.DataContractSerializer> imposta sempre correttamente i valori dei membri mancanti.  
  
### <a name="interaction-with-isrequired"></a>Interazione con IsRequired  
 Come descritto in [controllo delle versioni dei contratti dati](data-contract-versioning.md), l' <xref:System.Runtime.Serialization.DataMemberAttribute> attributo ha una <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> Proprietà (il valore predefinito è `false` ). indica se un determinato membro dati deve essere presente nei dati serializzati quando viene deserializzato. Se la proprietà `IsRequired` viene impostata su `true` (a indicare che un valore deve essere presente) e la proprietà <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> viene impostata su `false` (a indicare che il valore non deve essere presente se è impostato sul valore predefinito), i valori predefiniti del membro dati non possono essere serializzati perché i risultati sarebbero contraddittori. Se il membro dati è impostato sul valore predefinito (in genere `null` o zero) e si tenta di eseguire una serializzazione, viene generata un'eccezione <xref:System.Runtime.Serialization.SerializationException>.  
  
### <a name="schema-representation"></a>Rappresentazione dello schema  
 I dettagli della rappresentazione dello schema XSD (XML Schema Definition Language) dei membri dati quando la `EmitDefaultValue` proprietà è impostata su `false` sono descritti in [riferimento allo schema del contratto dati](data-contract-schema-reference.md). Di seguito viene invece fornita una descrizione di carattere più generale:  
  
- Quando <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> è impostato su `false` , viene rappresentato nello schema come un'annotazione specifica per Windows Communication Foundation (WCF). Non esiste alcuna modalità interoperativa per rappresentare queste informazioni. In particolare, l'attributo "default" dello schema non viene utilizzato per indicare un valore predefinito, l'attributo `minOccurs` dipende esclusivamente dall'impostazione <xref:System.Runtime.Serialization.DataMemberAttribute.IsRequired%2A> e l'attributo `nillable` dipende soltanto dal tipo del membro dati.  
  
- Il valore predefinito effettivo da utilizzare non è presente nello schema. La corretta impostazione di un elemento mancante spetta all'endpoint di destinazione.  
  
 Durante l'importazione dello schema, la <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A> proprietà viene impostata automaticamente su `false` ogni volta che viene rilevata l'annotazione specifica di WCF indicata in precedenza. Viene inoltre impostata su `false` per i tipi di riferimento la cui `nillable` proprietà è impostata su `false` per supportare scenari di interoperabilità specifici che in genere si verificano durante l'utilizzo dei servizi Web ASP.NET.  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.Serialization.DataMemberAttribute.EmitDefaultValue%2A>
- <xref:System.Runtime.Serialization.DataMemberAttribute>
