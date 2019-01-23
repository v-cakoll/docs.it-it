---
title: 'Procedura: Eseguire il mapping di relazioni tra Database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: 907ed58e9828921585135f2319d0db9559b606d3
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556382"
---
# <a name="how-to-map-database-relationships"></a>Procedura: Eseguire il mapping di relazioni tra Database
Qualsiasi relazione tra i dati, che rimane prevedibilmente sempre la stessa, può essere codificata come riferimenti alla proprietà nella classe di entità. Nel database di esempio Northwind, ad esempio, poiché in genere i clienti effettuano ordini, nel modello è sempre presente una relazione tra clienti e ordini.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definisce un <xref:System.Data.Linq.Mapping.AssociationAttribute> attributo per rappresentare tali relazioni. Questo attributo viene usato insieme ai tipi <xref:System.Data.Linq.EntitySet%601> e <xref:System.Data.Linq.EntityRef%601> per rappresentare quello che in un database sarebbe una relazione di chiave esterna. Per altre informazioni, vedere la sezione relativa all'attributo Association di [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
>  I valori delle proprietà di archiviazione AssociationAttribute e ColumnAttribute rispettano la distinzione tra maiuscole e minuscole. Verificare, ad esempio, che per i valori dell'attributo della proprietà AssociationAttribute.Storage venga usata la stessa combinazione di maiuscole e minuscole adoperata per i nomi di proprietà corrispondenti usati in altri punti del codice. Questo vale per tutti i linguaggi di programmazione .NET, anche quelli che non sono in genere tra maiuscole e minuscole, tra cui Visual Basic. Per altre informazioni sulla proprietà di archiviazione, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 La maggior parte delle relazioni è di tipo uno-a-molti, come nell'esempio riportato più avanti in questo argomento. È anche possibile rappresentare relazioni uno-a-uno e molti-a-molti come segue:  
  
-   Uno a uno: Rappresentare questo tipo di relazione includendo <xref:System.Data.Linq.EntitySet%601> su entrambi i lati.  
  
     Si consideri, ad esempio, un `Customer` - `SecurityCode` relazione, creato in modo che il codice di sicurezza del cliente non verrà trovato nel `Customer` tabella ed è accessibile solo da utenti autorizzati.  
  
-   Molti-a-molti: In una relazione molti-a-molti, la chiave primaria della tabella dei collegamenti (anche denominato il *giunzione* tabella) è spesso formata da una combinazione di chiavi esterne delle altre due tabelle.  
  
     Si consideri, ad esempio, un' `Employee` - `Project` relazione molti-a-molti formate usando tabella dei collegamenti `EmployeeProject`. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è necessario che tale relazione venga modellata usando tre classi:`Employee`, `Project` e `EmployeeProject`. In questo caso la modifica della relazione tra `Employee` e `Project` può apparentemente richiedere un aggiornamento della chiave primaria di `EmployeeProject`. In questa situazione, tuttavia, è preferibile modellare la relazione eliminando una classe `EmployeeProject` esistente e creando una nuova classe `EmployeeProject`.  
  
    > [!NOTE]
    >  Le relazioni nei database relazionali vengono in genere modellate come valori di chiave esterna che fanno riferimento a chiavi primarie in altre tabelle. Per spostarsi tra di essi si associano in modo esplicito le due tabelle usando una relazionale *join* operazione.  
    >   
    >  Gli oggetti nello [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], da altra parte, fanno riferimento reciproco usando riferimenti alle proprietà o raccolte di riferimenti che è possibile spostarsi utilizzando *dot* notation.  
  
## <a name="example"></a>Esempio  
 Nell'esempio uno-a-molti seguente, alla classe `Customer` è associata una proprietà che dichiara la relazione tra clienti e ordini.  La proprietà `Orders` è di tipo <xref:System.Data.Linq.EntitySet%601>. Questo tipo significa che si tratta di una relazione uno-a-molti (un cliente a molti ordini). La proprietà <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> viene usata per descrivere come viene eseguita questa associazione, ovvero specificando il nome della proprietà nella classe correlata che dovrà essere confrontata con questa. In questo esempio, il `CustomerID` proprietà verrà confrontata, proprio come un database *join* verrebbe confrontato il valore di tale colonna.  
  
> [!NOTE]
>  Se si usa Visual Studio, è possibile usare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per creare un'associazione tra classi.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Esempio  
 È anche possibile invertire la situazione. Anziché usare la classe `Customer` per descrivere l'associazione tra clienti e ordini, è possibile usare la classe `Order`. La classe `Order` usa il tipo <xref:System.Data.Linq.EntityRef%601> per descrivere la relazione con la classe Customer, come nell'esempio di codice seguente.  
  
> [!NOTE]
>  Il <xref:System.Data.Linq.EntityRef%601> supportate dalla classe *caricamento posticipato*. Per altre informazioni, *visualizzare* [posticipato e immediato caricamento](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Personalizzare le classi di entità usando l'Editor di codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
