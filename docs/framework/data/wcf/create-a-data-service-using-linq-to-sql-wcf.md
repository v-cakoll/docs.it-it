---
title: "Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL (WCF Data Services)"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, LINQ to SQL
- WCF Data Services, providers
ms.assetid: 3b01c2fd-8c6e-4bf5-b38f-9e61bdc3c328
ms.openlocfilehash: cde5b9903a1fd164ce106a6a408ac4bb79976642
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "74802288"
---
# <a name="how-to-create-a-data-service-using-a-linq-to-sql-data-source-wcf-data-services"></a>Procedura: creare un servizio dati tramite un'origine dati LINQ to SQL (WCF Data Services)

WCF Data Services espone i dati di entità come servizio dati. Il provider di reflection consente di definire un modello di dati basato su qualsiasi classe che espone i membri che restituiscono un'implementazione di <xref:System.Linq.IQueryable%601>. Per essere in grado di apportare aggiornamenti ai dati nell'origine dati, queste classi devono inoltre implementare l'interfaccia <xref:System.Data.Services.IUpdatable>. Per ulteriori informazioni, vedere [provider di servizi dati](data-services-providers-wcf-data-services.md). In questo argomento viene illustrato come creare classi LINQ to SQL per l'accesso al database Northwind di esempio tramite il provider di reflection, nonché come creare il servizio dati basato su queste classi di dati.

## <a name="to-add-linq-to-sql-classes-to-a-project"></a>Per aggiungere classi LINQ to SQL a un progetto

1. Dall'interno di un Visual Basic C# o di un'applicazione scegliere **Aggiungi** > **nuovo elemento**dal menu **progetto** .

2. Fare clic sul modello **classi LINQ to SQL** .

3. Modificare il nome in **Northwind. dbml**.

4. Fare clic su **Aggiungi**.

     Il file Northwind.dbml verrà aggiunto al progetto e verrà visualizzato Progettazione relazionale oggetti.

5. In **Server**/**Esplora database**, in Northwind, espandere **tabelle** e trascinare la tabella `Customers` nel Object Relational Designer (O/R Designer).

     Verrà creata una classe di entità `Customer` che verrà visualizzata nell'area di progettazione.

6. Ripetere il passaggio 6 per le tabelle `Orders`, `Order_Details` e `Products`.

7. Fare clic con il pulsante destro del mouse sul nuovo file con estensione dbml che rappresenta le classi LINQ to SQL e scegliere **Visualizza codice**.

     Verrà creata una nuova pagina code-behind denominata Northwind.cs contenente una definizione di classe parziale per la classe che eredita dalla classe <xref:System.Data.Linq.DataContext>, che in questo caso corrisponde a `NorthwindDataContext`.

8. Sostituire il contenuto del file di codice Northwind.cs con il codice riportato di seguito. Questo codice implementa il provider di reflection mediante l'estensione di <xref:System.Data.Linq.DataContext> e delle classi di dati generate da LINQ to SQL:

     [!code-csharp[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.cs#linq2sqlprovider)]
     [!code-vb[Astoria Linq Provider#Linq2SqlProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.vb#linq2sqlprovider)]

### <a name="to-create-a-data-service-by-using-a-linq-to-sql-based-data-model"></a>Per creare un servizio dati tramite un modello di dati basato su LINQ to SQL

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul nome del progetto ASP.NET, quindi scegliere **Aggiungi** > **nuovo elemento**.

2. Nella finestra di dialogo **Aggiungi nuovo elemento** selezionare il modello di **servizio dati WCF** dalla categoria **Web** .

   ![Modello di elemento del servizio dati WCF in Visual Studio 2015](./media/wcf-data-service-item-template.png)

   > [!NOTE]
   > Il modello di **servizio dati WCF** è disponibile in visual studio 2015, ma non in visual studio 2017 o versioni successive.

3. Specificare un nome per il servizio, quindi fare clic su **OK**.

     In Visual Studio verranno creati i file del markup XML e del codice per il nuovo servizio. Per impostazione predefinita, verrà visualizzata la finestra dell'editor del codice.

4. Nel codice per il servizio dati sostituire il commento `/* TODO: put your data source class name here */` nella definizione della classe che definisce il servizio dati con il tipo del contenitore di entità del modello di dati, che in questo caso corrisponde a `NorthwindDataContext`.

5. Nel codice per il servizio dati sostituire il codice segnaposto nella funzione `InitializeService` con il codice seguente:

     [!code-csharp[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_linq_provider/cs/northwind.svc.cs#enableaccess)]
     [!code-vb[Astoria Linq Provider#EnableAccess](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_linq_provider/vb/northwind.svc.vb#enableaccess)]

     In questo modo i client autorizzati saranno in grado di accedere alle risorse per i tre set di entità specificati.

6. Per testare il servizio dati Northwind. svc utilizzando una Web browser, seguire le istruzioni riportate nell'argomento [accesso al servizio da un Web browser](accessing-the-service-from-a-web-browser-wcf-data-services-quickstart.md).

## <a name="see-also"></a>Vedere anche

- [Procedura: creare un servizio dati tramite un'origine dati ADO.NET Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md)
- [Procedura: creare un servizio dati tramite il provider di reflection](create-a-data-service-using-rp-wcf-data-services.md)
- [Provider di servizi dati](data-services-providers-wcf-data-services.md)
