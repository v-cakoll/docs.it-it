---
title: Modello a oggetti LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 81dd0c37-e2a4-4694-83b0-f2e49e693810
ms.openlocfilehash: 7ce759de004d479f5162d2ce3a965f5c40afa450
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61917602"
---
# <a name="the-linq-to-sql-object-model"></a>Modello a oggetti LINQ to SQL
In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], viene eseguito il mapping di un modello a oggetti espresso nel linguaggio di programmazione dello sviluppatore al modello di dati di un database relazionale. Le operazioni sui dati vengono quindi eseguite in base al modello a oggetti.  
  
 In questo scenario non vengono eseguiti comandi di database, ad esempio `INSERT`, sul database, bensì vengono modificati valori ed eseguiti metodi all'interno del modello a oggetti. Quando si desidera eseguire una query sul database o inviare modifiche al database, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] converte le richieste in comandi SQL corretti che vengono quindi inviati al database.  
  
 ![DLinqObjectModel](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinqobjectmodel.png "DLinqObjectModel")  
  
 Gli elementi più importanti nel [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modello a oggetti e la loro relazione con gli elementi del modello di dati relazionali sono riepilogati nella tabella riportata di seguito:  
  
|Modello a oggetti LINQ to SQL|Modello dati relazionale|  
|------------------------------|---------------------------|  
|Classe di entità|Tabella|  
|Membro di classe|Colonna|  
|Associazione|Relazione di chiave esterna|  
|Metodo|Stored procedure o funzione|  
  
> [!NOTE]
>  Nelle descrizioni seguenti si presuppone una conoscenza di base del modello dati relazionale e delle regole.  
  
## <a name="linq-to-sql-entity-classes-and-database-tables"></a>Classi di entità LINQ to SQL e tabelle di database  
 Nelle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], una tabella di database è rappresentata da un' *classe di entità*. Una classe di entità è analoga a qualsiasi altra classe creata dallo sviluppatore, con l'eccezione che per annotare la classe vengono usate informazioni speciali che associano la classe a una tabella di database. Per creare tale annotazione, aggiungere un attributo personalizzato (<xref:System.Data.Linq.Mapping.TableAttribute>) alla dichiarazione della classe, come nell'esempio seguente:  
  
### <a name="example"></a>Esempio  
 [!code-csharp[DLinqObjectModel#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#1)]
 [!code-vb[DLinqObjectModel#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#1)]  
  
 Solo le istanze delle classi dichiarate come tabelle, ovvero le classi di entità, possono essere salvate nel database.  
  
 Per altre informazioni, vedere la sezione relativa all'attributo di tabella di [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-class-members-and-database-columns"></a>Membri di classe LINQ to SQL e colonne di database  
 Oltre all'associazione delle classi con le tabelle, è necessario definire i campi o le proprietà per rappresentare le colonne del database. A questo scopo in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] viene definito l'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute>, come nell'esempio seguente:  
  
### <a name="example"></a>Esempio  
 [!code-csharp[DLinqObjectModel#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/Program.cs#2)]
 [!code-vb[DLinqObjectModel#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/Module1.vb#2)]  
  
 Solo i campi e le proprietà di cui è stato eseguito il mapping alle colonne vengono salvati in modo permanente o recuperati dal database. Quelli non dichiarati come colonne vengono considerati parti temporanee della logica dell'applicazione.  
  
 All'attributo <xref:System.Data.Linq.Mapping.ColumnAttribute> sono associate diverse proprietà che è possibile usare per personalizzare i membri che rappresentano colonne, ad esempio definendo un membro che rappresenta una colonna di chiave primaria. Per altre informazioni, vedere la sezione relativa all'attributo di colonna di [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-associations-and-database-foreign-key-relationships"></a>Associazioni LINQ to SQL e relazioni di chiave esterna del database  
 Nelle [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], si rappresentano le associazioni di database (ad esempio, chiave esterna per le relazioni di chiave primaria) applicando il <xref:System.Data.Linq.Mapping.AssociationAttribute> attributo. Nel seguente segmento di codice, il `Order` classe contiene una `Customer` proprietà con un <xref:System.Data.Linq.Mapping.AssociationAttribute> attributo. Questa proprietà e il relativo attributo forniscono la classe `Order` con una relazione alla classe `Customer`.  
  
 Nell'esempio di codice riportato di seguito viene illustrata la proprietà `Customer` della classe `Order`.  
  
### <a name="example"></a>Esempio  
 [!code-csharp[DLinqObjectModel#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#3)]
 [!code-vb[DLinqObjectModel#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#3)]  
  
 Per altre informazioni, vedere la sezione relativa all'attributo Association di [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
## <a name="linq-to-sql-methods-and-database-stored-procedures"></a>Metodi LINQ to SQL e stored procedure di database  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] supporta stored procedure e funzioni definite dall'utente. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], si esegue il mapping queste astrazioni definite dal database per gli oggetti client in modo che è possibile accedervi in modo fortemente tipizzato dal codice client. Le firme del metodo sono quanto più possibile simili alle firme delle procedure e delle funzioni definite nel database. Per individuare questi metodi è possibile usare IntelliSense.  
  
 Un set di risultati restituito da una chiamata a una procedura con mapping è una raccolta fortemente tipizzata.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] esegue il mapping di stored procedure e funzioni ai metodi usando gli attributi <xref:System.Data.Linq.Mapping.FunctionAttribute> e <xref:System.Data.Linq.Mapping.ParameterAttribute>. I metodi che rappresentano stored procedure si differenziano da quelli che rappresentano funzioni definite dall'utente per la proprietà <xref:System.Data.Linq.Mapping.FunctionAttribute.IsComposable%2A>. Se questa proprietà è impostata su `false`, che corrisponde all'impostazione predefinita, il metodo rappresenta una stored procedure. Se è impostata su `true`, il metodo rappresenta una funzione di database.  
  
> [!NOTE]
>  Se si usa Visual Studio, è possibile usare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] creare metodi con mappati a stored procedure e funzioni definite dall'utente.  
  
### <a name="example"></a>Esempio  
 [!code-csharp[DLinqObjectModel#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqObjectModel/cs/northwind.cs#4)]
 [!code-vb[DLinqObjectModel#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqObjectModel/vb/northwind.vb#4)]  
  
 Per altre informazioni, vedere le sezioni di attributo della funzione, Stored Procedure e attributo di parametro del [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md) e [Stored Procedures](../../../../../../docs/framework/data/adonet/sql/linq/stored-procedures.md).  
  
## <a name="see-also"></a>Vedere anche

- [Mapping basato su attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
