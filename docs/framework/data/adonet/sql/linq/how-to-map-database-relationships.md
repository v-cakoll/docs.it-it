---
title: 'Procedura: eseguire il mapping di relazioni tra database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: c89fb3e11ae8e0f8ea37727446cdf65db9499a1d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148374"
---
# <a name="how-to-map-database-relationships"></a>Procedura: eseguire il mapping di relazioni tra database
Qualsiasi relazione tra i dati, che rimane prevedibilmente sempre la stessa, può essere codificata come riferimenti alla proprietà nella classe di entità. Nel database di esempio Northwind, ad esempio, poiché in genere i clienti effettuano ordini, nel modello è sempre presente una relazione tra clienti e ordini.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]definisce <xref:System.Data.Linq.Mapping.AssociationAttribute> un attributo per facilitare la rappresentazione di tali relazioni. Questo attributo viene utilizzato insieme ai tipi <xref:System.Data.Linq.EntitySet%601> e <xref:System.Data.Linq.EntityRef%601> per rappresentare quello che in un database sarebbe una relazione di chiave esterna. Per ulteriori informazioni, vedere la sezione Attributo di associazione di [Mapping basato su attributi](attribute-based-mapping.md).  
  
> [!NOTE]
> I valori delle proprietà di archiviazione AssociationAttribute e ColumnAttribute rispettano la distinzione tra maiuscole e minuscole. Verificare, ad esempio, che per i valori dell'attributo della proprietà AssociationAttribute.Storage venga usata la stessa combinazione di maiuscole e minuscole adoperata per i nomi di proprietà corrispondenti usati in altri punti del codice. Questo vale per tutti i linguaggi di programmazione .NET, anche quelli che in genere non fanno distinzione tra maiuscole e minuscole, incluso Visual Basic. Per altre informazioni sulla proprietà di archiviazione, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 La maggior parte delle relazioni è di tipo uno-a-molti, come nell'esempio riportato più avanti in questo argomento. È anche possibile rappresentare relazioni uno-a-uno e molti-a-molti come segue:  
  
- Uno-a-uno: per rappresentare questo tipo di relazione includere <xref:System.Data.Linq.EntitySet%601> su entrambi i lati.  
  
     Si consideri, `Customer` - `SecurityCode` ad esempio, una relazione creata in modo che `Customer` il codice di sicurezza del cliente non venga trovato nella tabella e sia accessibile solo a persone autorizzate.  
  
- Molti-a-molti: nelle relazioni molti-a-molti, la chiave primaria della tabella di collegamento (denominata anche tabella di *collegamento)* è spesso formata da un composto delle chiavi esterne delle altre due tabelle.  
  
     Si consideri, `Employee` - `Project` ad esempio, una relazione molti-a-molti formata utilizzando la tabella `EmployeeProject`dei collegamenti . In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è necessario che tale relazione venga modellata usando tre classi:`Employee`, `Project` e `EmployeeProject`. In questo caso la modifica della relazione tra `Employee` e `Project` può apparentemente richiedere un aggiornamento della chiave primaria di `EmployeeProject`. In questa situazione, tuttavia, è preferibile modellare la relazione eliminando una classe `EmployeeProject` esistente e creando una nuova classe `EmployeeProject`.  
  
    > [!NOTE]
    > Le relazioni nei database relazionali vengono in genere modellate come valori di chiave esterna che fanno riferimento a chiavi primarie in altre tabelle. Per spostarsi tra di esse, associare in modo esplicito le due tabelle utilizzando un'operazione di *join relazionale.*  
    >
    >  Gli [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]oggetti in , d'altra parte, fanno riferimento l'uno all'altro utilizzando riferimenti di proprietà o raccolte di riferimenti che si spostano utilizzando la notazione *del punto.*  
  
## <a name="example"></a>Esempio  
 Nell'esempio uno-a-molti seguente, alla classe `Customer` è associata una proprietà che dichiara la relazione tra clienti e ordini.  La proprietà `Orders` è di tipo <xref:System.Data.Linq.EntitySet%601>. Questo tipo significa che si tratta di una relazione uno-a-molti (un cliente a molti ordini). La proprietà <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> viene usata per descrivere come viene eseguita questa associazione, ovvero specificando il nome della proprietà nella classe correlata che dovrà essere confrontata con questa. In questo esempio, la `CustomerID` proprietà viene confrontata, proprio come un *join* di database confronta il valore di colonna.  
  
> [!NOTE]
> Se si utilizza Visual Studio, è possibile utilizzare Object Relational Designer per creare un'associazione tra classi.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Esempio  
 È inoltre possibile invertire la situazione. Anziché usare la classe `Customer` per descrivere l'associazione tra clienti e ordini, è possibile usare la classe `Order`. La classe `Order` usa il tipo <xref:System.Data.Linq.EntityRef%601> per descrivere la relazione con la classe Customer, come nell'esempio di codice seguente.  
  
> [!NOTE]
> La <xref:System.Data.Linq.EntityRef%601> classe supporta il *caricamento posticipato.* Per ulteriori informazioni, *vedere* [Caricamento posticipato e immediato](deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: personalizzare classi di entità mediante l'Editor del codice](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Modello a oggetti LINQ to SQL](the-linq-to-sql-object-model.md)
