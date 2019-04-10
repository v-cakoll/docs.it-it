---
title: 'Procedura dettagliata: Esecuzione di query tra relazioni (C#)'
ms.date: 03/30/2017
ms.assetid: 552abeb1-18f2-4e93-a9c6-ef7b2db30c32
ms.openlocfilehash: 6bd3255b49676b61a99f8416ab71c217d342e799
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/09/2019
ms.locfileid: "59325371"
---
# <a name="walkthrough-querying-across-relationships-c"></a>Procedura dettagliata: Esecuzione di query tra relazioni (C#)
Questa procedura dettagliata viene illustrato come utilizzare [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] *associazioni* per rappresentare le relazioni di chiave esterna nel database.  
  
 [!INCLUDE[note_settings_general](../../../../../../includes/note-settings-general-md.md)]  
  
 Questa procedura è stata scritta usando Impostazioni di sviluppo di Visual C#.  
  
## <a name="prerequisites"></a>Prerequisiti  
 È necessario avere completato [procedura dettagliata: Modello a oggetti semplice ed eseguire una Query (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-simple-object-model-and-query-csharp.md). Questa procedura dettagliata si basa su tale procedura dettagliata, inclusa la presenza del file northwnd.mdf in c:\linqtest5.  
  
## <a name="overview"></a>Panoramica  
 La procedura dettagliata è costituita da tre attività principali:  
  
-   Aggiunta di una classe di entità per rappresentare la tabella Orders nel database di esempio Northwind.  
  
-   Completamento delle annotazioni alla classe `Customer` per migliorare la relazione tra le classi `Customer` e `Order`.  
  
-   Creazione ed esecuzione di una query per testare la capacità di ottenere informazioni su `Order` usando la classe `Customer`.  
  
## <a name="mapping-relationships-across-tables"></a>Esecuzione del mapping delle relazioni tra tabelle  
 Dopo la definizione della classe `Customer`, creare la definizione della classe di entità `Order` includendo il codice seguente per indicare che `Order.Customer` è correlata come chiave esterna a `Customer.CustomerID`.  
  
#### <a name="to-add-the-order-entity-class"></a>Per aggiungere la classe di entità Order  
  
-   Digitare o incollare il codice seguente dopo la classe `Customer`:  
  
     [!code-csharp[DLinqWalk2CS#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#1)]  
  
## <a name="annotating-the-customer-class"></a>Annotazione della classe Customer  
 In questo passaggio vengono aggiunte annotazioni alla classe `Customer` per indicare la relazione alla classe `Order`. Questa aggiunta non è strettamente necessaria, in quanto la definizione della relazione in una direzione è sufficiente per creare il collegamento. Tuttavia aggiungendo l'annotazione sarà possibile spostarsi facilmente tra gli oggetti in entrambe le direzioni.  
  
#### <a name="to-annotate-the-customer-class"></a>Per annotare la classe Customer  
  
-   Digitare o incollare il codice seguente nella classe `Customer`:  
  
     [!code-csharp[DLinqWalk2CS#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#2)]  
  
## <a name="creating-and-running-a-query-across-the-customer-order-relationship"></a>Creazione ed esecuzione di un query sulla relazione Customer-Order  
 A questo punto è possibile accedere direttamente agli oggetti `Order` dagli oggetti `Customer` o viceversa. Non è necessaria l'esplicita *join* tra customers e orders.  
  
#### <a name="to-access-order-objects-by-using-customer-objects"></a>Per accedere agli oggetti Order usando oggetti Customer  
  
1. Modificare il metodo `Main` digitando o incollando il codice seguente nel metodo stesso:  
  
     [!code-csharp[DLinqWalk2CS#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#3)]  
  
2. Premere F5 per eseguire il debug dell'applicazione.  
  
    > [!NOTE]
    >  È possibile eliminare il codice SQL nella finestra della console impostando come commento `db.Log = Console.Out;`.  
  
3. Premere INVIO nella finestra della console per terminare il debug.  
  
## <a name="creating-a-strongly-typed-view-of-your-database"></a>Creazione di una visualizzazione fortemente tipizzata del database  
 È molto più facile iniziare con una visualizzazione fortemente tipizzata del database. Applicando la tipizzazione forte all'oggetto <xref:System.Data.Linq.DataContext>, si eviterà di eseguire chiamate a <xref:System.Data.Linq.DataContext.GetTable%2A>. Quando si usa l'oggetto fortemente tipizzato <xref:System.Data.Linq.DataContext>, è possibile usare tabelle fortemente tipizzate in tutte le query.  
  
 Nei passaggi seguenti si creerà `Customers` come tabella fortemente tipizzata mappata alla tabella Customers nel database.  
  
#### <a name="to-strongly-type-the-datacontext-object"></a>Per tipizzare fortemente l'oggetto DataContext  
  
1. Aggiungere il codice riportato di seguito sopra la dichiarazione della classe `Customer`.  
  
     [!code-csharp[DLinqWalk2CS#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#4)]  
  
2. Per usare l'oggetto fortemente tipizzato `Main`, modificare il metodo <xref:System.Data.Linq.DataContext> come segue:  
  
     [!code-csharp[DLinqWalk2CS#5](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqWalk2CS/cs/Program.cs#5)]  
  
3. Premere F5 per eseguire il debug dell'applicazione.  
  
     L'output nella finestra della console sarà:  
  
     `ID=WHITC`  
  
4. Premere INVIO nella finestra della console per terminare il debug.  
  
## <a name="next-steps"></a>Passaggi successivi  
 Procedura dettagliata seguente ([procedura dettagliata: Gestione dei dati (C#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-manipulating-data-csharp.md)) viene illustrato come modificare i dati. Per tale procedura dettagliata non è necessario avere salvato le due procedure dettagliate di questa serie già completate.  
  
## <a name="see-also"></a>Vedere anche

- [Apprendimento tramite procedure dettagliate](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
