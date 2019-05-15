---
title: ADO.NET e LINQ to SQL
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 49f28acc5001d63e7a1f6a5bfe8cb3415311e379
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65582745"
---
# <a name="adonet-and-linq-to-sql"></a>ADO.NET e LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] fa parte di [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] della famiglia di tecnologie. e si basa sui servizi forniti dal modello provider [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]. È pertanto possibile combinare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] codice esistenti [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] applicazioni ed eseguire la migrazione corrente [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] soluzioni [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]. Nell'illustrazione seguente viene fornita una panoramica della relazione.  
  
 ![LINQ to SQL e ADO.NET](../../../../../../docs/framework/data/adonet/sql/linq/media/dlinq-3.png "DLinq_3")  
  
## <a name="connections"></a>Connessioni  
 È possibile fornire un oggetto esistente [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] connessione quando si crea un' [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>. Tutte le operazioni contro il <xref:System.Data.Linq.DataContext> (incluse le query) usare la connessione specificata. Se la connessione è già aperta, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] lascia così com'è quando Usa più.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 È comunque possibile accedere alla connessione e chiuderla usando la proprietà <xref:System.Data.Linq.DataContext.Connection%2A>, come nel codice seguente:  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a>Transazioni  
 È possibile fornire l'oggetto <xref:System.Data.Linq.DataContext> con la transazione di database personalizzata qualora l'applicazione abbia già avviato la transazione e si desideri che venga usato anche <xref:System.Data.Linq.DataContext>.  
  
 Il metodo preferito di creare transazioni con .NET Framework consiste nell'usare il <xref:System.Transactions.TransactionScope> oggetto. Usando questo approccio, è possibile creare transazioni distribuite che potranno essere usate sia con database che con altri gestori di risorse residenti in memoria. Gli ambiti di transazione richiedono alcune risorse per iniziare. Vengono promossi a transazioni distribuite solo quando sono presenti più connessioni all'interno dell'ambito della transazione.  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 Non è possibile usare questo approccio per tutti i database. Ad esempio, la connessione di SqlClient non consente di promuovere transazioni di sistema quando viene usata con un server [!INCLUDE[ss2k](../../../../../../includes/ss2k-md.md)]. Al contrario, viene inserita automaticamente in una transazione distribuita completa quando viene rilevato l'uso di un ambito della transazione.  
  
## <a name="direct-sql-commands"></a>Comandi SQL diretti  
 In alcune situazioni la capacità di <xref:System.Data.Linq.DataContext> di eseguire query o inviare modifiche è insufficiente per l'attività specifica che si desidera eseguire. In queste circostanze è possibile usare il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> per inviare comandi SQL al database e convertire i risultati della query in oggetti.  
  
 Ad esempio, si supponga che i dati per la classe `Customer` siano distribuiti in due tabelle (customer1 e customer2). La query seguente consente di restituire una sequenza di oggetti `Customer`:  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 Purché i nomi di colonna nei risultati tabulari corrispondano alle proprietà di colonna della classe di entità, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creati oggetti da qualsiasi query SQL.  
  
### <a name="parameters"></a>Parametri  
 Il metodo <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> accetta l'uso di parametri. Nel codice seguente viene eseguita una query con parametri:  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
>  I parametri sono espressi nel testo della query usando la stessa notazione con parentesi graffe usata da `Console.WriteLine()` e `String.Format()`. `String.Format()` sostituisce quindi i parametri con parentesi graffe presenti nella stringa fornita con nomi di parametro generati, ad esempio `@p0`, `@p1` …, `@p(n)`.  
  
## <a name="see-also"></a>Vedere anche

- [Informazioni di base](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)
- [Procedura: Riutilizzare una connessione tra un comando ADO.NET e un DataContext](../../../../../../docs/framework/data/adonet/sql/linq/how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
