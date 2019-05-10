---
title: 'Procedura dettagliata: Eseguire query tra relazioni (Visual Basic)'
ms.date: 03/30/2017
dev_langs:
- vb
ms.assetid: a7da43e3-769f-4e07-bcd6-552b8bde66f4
ms.openlocfilehash: 0852622811b5efb362937b3af37f2b9d81b2d1ea
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64626432"
---
# <a name="walkthrough-querying-across-relationships-visual-basic"></a>Procedura dettagliata: Eseguire query tra relazioni (Visual Basic)
Questa procedura dettagliata viene illustrato come utilizzare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associazioni* per rappresentare le relazioni di chiave esterna nel database.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Questa procedura dettagliata è stata scritta usando Impostazioni di sviluppo di Visual Basic.  
  
## <a name="prerequisites"></a>Prerequisiti  
 È necessario avere completato [procedura dettagliata: Query (Visual Basic) e modello a oggetti semplice](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-visual-basic.md). Questa procedura dettagliata si basa su tale procedura dettagliata, inclusa la presenza del file northwnd.mdf in c:\linqtest.  
  
## <a name="overview"></a>Panoramica  
 La procedura dettagliata è costituita da tre attività principali:  
  
- Aggiunta di una classe di entità per rappresentare la tabella Orders nel database di esempio Northwind.  
  
- Completamento delle annotazioni alla classe `Customer` per migliorare la relazione tra le classi `Customer` e `Order`.  
  
- Creazione ed esecuzione di una query per testare il processo per ottenere informazioni su `Order` usando la classe `Customer`.  
  
## <a name="mapping-relationships-across-tables"></a>Esecuzione del mapping delle relazioni tra tabelle  
 Dopo la definizione della classe `Customer`, creare la definizione della classe di entità `Order` includendo il codice seguente per indicare che `Orders.Customer` è correlata come chiave esterna a `Customers.CustomerID`.  
  
#### <a name="to-add-the-order-entity-class"></a>Per aggiungere la classe di entità Order  
  
- Digitare o incollare il codice seguente dopo la classe `Customer`:  
  
     [!code-vb[DLinqWalk2VB#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#1)]  
  
## <a name="annotating-the-customer-class"></a>Annotazione della classe Customer  
 In questo passaggio vengono aggiunte annotazioni alla classe `Customer` per indicare la relazione alla classe `Order`. Questa aggiunta non è strettamente necessaria, in quanto la definizione della relazione in una direzione è sufficiente per creare il collegamento. Tuttavia aggiungendo l'annotazione sarà possibile spostarsi facilmente tra gli oggetti in entrambe le direzioni.  
  
#### <a name="to-annotate-the-customer-class"></a>Per annotare la classe Customer  
  
- Digitare o incollare il codice seguente nella classe `Customer`:  
  
     [!code-vb[DLinqWalk2VB#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a>Creazione ed esecuzione di un query sulla relazione Customer-Order  
 A questo punto è possibile accedere direttamente agli oggetti `Order` dagli oggetti `Customer` o viceversa. Non è necessaria l'esplicita *join* tra customers e orders.  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a>Per accedere agli oggetti Order usando oggetti Customer  
  
1. Modificare il metodo `Sub Main` digitando o incollando il codice seguente nel metodo stesso:  
  
     [!code-vb[DLinqWalk2VB#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#3)]  
  
2. Premere F5 per eseguire il debug dell'applicazione.  
  
     Nella finestra di messaggio vengono visualizzati due nomi, mentre nella finestra della console viene riportato il codice SQL generato.  
  
3. Chiudere la finestra di messaggio per interrompere il debug.  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a>Creazione di una visualizzazione fortemente tipizzata del database  
 È molto più facile iniziare con una visualizzazione fortemente tipizzata del database. Applicando la tipizzazione forte all'oggetto <xref:System.Data.Linq.DataContext>, si eviterà di eseguire chiamate a <xref:System.Data.Linq.DataContext.GetTable%2A>. Quando si usa l'oggetto fortemente tipizzato <xref:System.Data.Linq.DataContext>, è possibile usare tabelle fortemente tipizzate in tutte le query.  
  
 Nei passaggi seguenti si creerà `Customers` come tabella fortemente tipizzata mappata alla tabella Customers nel database.  
  
#### <a name="to-strongly-type-the-datacontext-object"></a>Per tipizzare fortemente l'oggetto DataContext  
  
1. Aggiungere il codice riportato di seguito sopra la dichiarazione della classe `Customer`.  
  
     [!code-vb[DLinqWalk2VB#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#4)]  
  
2. Modificare `Sub Main` per usare l'oggetto fortemente tipizzato <xref:System.Data.Linq.DataContext> come segue:  
  
     [!code-vb[DLinqWalk2VB#5](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqWalk2VB/vb/Module1.vb#5)]  
  
3. Premere F5 per eseguire il debug dell'applicazione.  
  
     L'output nella finestra della console sarà:  
  
     `ID=WHITC`  
  
4. Premere INVIO nella finestra Console per chiudere l'applicazione.  
  
5. Nel **File** menu, fare clic su **Salva tutto** se si desidera salvare questa applicazione.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Procedura dettagliata seguente ([procedura dettagliata: Gestione dei dati (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-visual-basic.md)) viene illustrato come modificare i dati. Per tale procedura dettagliata non è necessario avere salvato le due procedure dettagliate di questa serie già completate.  
  
## <a name="see-also"></a>Vedere anche

- [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
