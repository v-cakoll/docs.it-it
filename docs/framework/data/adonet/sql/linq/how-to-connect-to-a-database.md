---
title: 'Procedura: connettersi a un database'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c33d74b3-530d-421b-a121-96786dd263a5
ms.openlocfilehash: 837919b1cfcdf46026ccfb37cbbec951c0ae41b8
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634677"
---
# <a name="how-to-connect-to-a-database"></a>Procedura: connettersi a un database
<xref:System.Data.Linq.DataContext> funge da canale principale per la connessione a un database, il recupero degli oggetti e l'invio delle modifiche. Usare il <xref:System.Data.Linq.DataContext> come si farebbe con un <xref:System.Data.SqlClient.SqlConnection>ADO.NET. L'inizializzazione di <xref:System.Data.Linq.DataContext>, infatti, viene effettuata con una connessione o una stringa di connessione specificata. Per altre informazioni, vedere [metodi DataContext (O/R Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer).  
  
 Lo scopo di <xref:System.Data.Linq.DataContext> consiste nel convertire le richieste di oggetti in query SQL da eseguire sul database, quindi di assemblare gli oggetti dai risultati. Il <xref:System.Data.Linq.DataContext> Abilita LINQ (Language-Integrated Query) implementando lo stesso modello di operatore degli operatori di query standard, ad esempio `Where` e `Select`.  
  
> [!IMPORTANT]
> La gestione di una connessione sicura è della massima importanza. Per ulteriori informazioni, vedere [sicurezza in LINQ to SQL](security-in-linq-to-sql.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene usato <xref:System.Data.Linq.DataContext> per effettuare la connessione al database di esempio Northwind e recuperare le righe dei clienti la cui città di residenza è London.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#1)]
 [!code-vb[DLinqCommunicatingWithDatabase#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#1)]  
  
 Ogni tabella di database è rappresentata come una raccolta `Table` disponibile tramite il metodo <xref:System.Data.Linq.DataContext.GetTable%2A> usando la classe di entità per identificarlo.  
  
## <a name="example"></a>Esempio  
 La procedura consigliata consiste nel dichiarare <xref:System.Data.Linq.DataContext> con una tipizzazione forte anziché basarsi sulla classe <xref:System.Data.Linq.DataContext> di base e sul metodo <xref:System.Data.Linq.DataContext.GetTable%2A>. La tipizzazione forte di<xref:System.Data.Linq.DataContext> consente di dichiarare tutte le raccolte `Table` come membri del contesto, come illustrato nell'esempio seguente.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#2)]
 [!code-vb[DLinqCommunicatingWithDatabase#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#2)]  
  
 È quindi possibile esprimere la query per i clienti dell'area londinese come:  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#5)]
 [!code-vb[DLinqCommunicatingWithDatabase#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#5)]  
  
## <a name="see-also"></a>Vedere anche

- [Comunicazione con il database](communicating-with-the-database.md)
