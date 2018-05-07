---
title: 'Procedura: eseguire il mapping di relazioni tra database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 538def39-8399-46fb-b02d-60ede4e050af
ms.openlocfilehash: c3ae138134682f35ae42c99cc6434dae9ec1103d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-map-database-relationships"></a>Procedura: eseguire il mapping di relazioni tra database
Qualsiasi relazione tra i dati, che rimane prevedibilmente sempre la stessa, può essere codificata come riferimenti alla proprietà nella classe di entità. Nel database di esempio Northwind, ad esempio, poiché in genere i clienti effettuano ordini, nel modello è sempre presente una relazione tra clienti e ordini.  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] definisce un <xref:System.Data.Linq.Mapping.AssociationAttribute> attributo consentono di rappresentare tali relazioni. Questo attributo viene usato insieme ai tipi <xref:System.Data.Linq.EntitySet%601> e <xref:System.Data.Linq.EntityRef%601> per rappresentare quello che in un database sarebbe una relazione di chiave esterna. Per ulteriori informazioni, vedere la sezione relativa all'attributo Association [Mapping basato sugli attributi](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md).  
  
> [!NOTE]
>  I valori delle proprietà di archiviazione AssociationAttribute e ColumnAttribute rispettano la distinzione tra maiuscole e minuscole. Verificare, ad esempio, che per i valori dell'attributo della proprietà AssociationAttribute.Storage venga usata la stessa combinazione di maiuscole e minuscole adoperata per i nomi di proprietà corrispondenti usati in altri punti del codice. Questo vale per tutti i linguaggi di programmazione .NET, anche quelli che non sono in genere tra maiuscole e minuscole, tra cui Visual Basic. Per altre informazioni sulla proprietà di archiviazione, vedere <xref:System.Data.Linq.Mapping.DataAttribute.Storage%2A?displayProperty=nameWithType>.  
  
 La maggior parte delle relazioni è di tipo uno-a-molti, come nell'esempio riportato più avanti in questo argomento. È anche possibile rappresentare relazioni uno-a-uno e molti-a-molti come segue:  
  
-   Uno-a-uno: per rappresentare questo tipo di relazione includere <xref:System.Data.Linq.EntitySet%601> su entrambi i lati.  
  
     Si consideri ad esempio un `Customer` - `SecurityCode` creati in modo che non verrà trovato il codice di sicurezza del cliente relazione la `Customer` tabella ed è possibile accedervi solo da persone autorizzate.  
  
-   Molti-a-molti: In relazioni molti-a-molti, la chiave primaria della tabella di collegamento (denominato anche il *giunzione* tabella) è spesso formata da una combinazione di chiavi esterne delle altre due tabelle.  
  
     Si consideri ad esempio un `Employee` - `Project` relazione molti-a-molti con tabella di collegamento `EmployeeProject`. In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] è necessario che tale relazione venga modellata usando tre classi:`Employee`, `Project` e `EmployeeProject`. In questo caso la modifica della relazione tra `Employee` e `Project` può apparentemente richiedere un aggiornamento della chiave primaria di `EmployeeProject`. In questa situazione, tuttavia, è preferibile modellare la relazione eliminando una classe `EmployeeProject` esistente e creando una nuova classe `EmployeeProject`.  
  
    > [!NOTE]
    >  Le relazioni nei database relazionali vengono in genere modellate come valori di chiave esterna che fanno riferimento a chiavi primarie in altre tabelle. Per spostarsi tra di esse è possibile associare in modo esplicito le due tabelle utilizzando relazionale *join* operazione.  
    >   
    >  Gli oggetti in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], d'altra parte, fanno riferimento reciproco usando riferimenti alle proprietà o raccolte di riferimenti che è possibile spostarsi utilizzando *punto* notazione.  
  
## <a name="example"></a>Esempio  
 Nell'esempio uno-a-molti seguente, alla classe `Customer` è associata una proprietà che dichiara la relazione tra clienti e ordini.  La proprietà `Orders` è di tipo <xref:System.Data.Linq.EntitySet%601>. Questo tipo significa che si tratta di una relazione uno-a-molti (un cliente a molti ordini). La proprietà <xref:System.Data.Linq.Mapping.AssociationAttribute.OtherKey%2A> viene usata per descrivere come viene eseguita questa associazione, ovvero specificando il nome della proprietà nella classe correlata che dovrà essere confrontata con questa. In questo esempio, il `CustomerID` proprietà verrà confrontata, come un database *join* verrebbe confrontato il valore di tale colonna.  
  
> [!NOTE]
>  Se si utilizza Visual Studio, è possibile utilizzare il [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] per creare un'associazione tra classi.  
  
 [!code-csharp[DlinqCustomize#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#3)]
 [!code-vb[DlinqCustomize#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#3)]  
  
## <a name="example"></a>Esempio  
 È anche possibile invertire la situazione. Anziché usare la classe `Customer` per descrivere l'associazione tra clienti e ordini, è possibile usare la classe `Order`. La classe `Order` usa il tipo <xref:System.Data.Linq.EntityRef%601> per descrivere la relazione con la classe Customer, come nell'esempio di codice seguente.  
  
> [!NOTE]
>  Il <xref:System.Data.Linq.EntityRef%601> classe supporta *il caricamento posticipato*. Per ulteriori informazioni, *vedere* [posticipata e il caricamento immediato](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md).  
  
 [!code-csharp[DLinqCustomize#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCustomize/cs/Program.cs#5)]
 [!code-vb[DLinqCustomize#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCustomize/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: personalizzare classi di entità mediante l'Editor del codice](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)  
 [Modello a oggetti LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
