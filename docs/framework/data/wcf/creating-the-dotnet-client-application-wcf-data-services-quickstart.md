---
title: Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 86ded7351d435b3a7077f0354d8a923b33a3f2b6
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/04/2018
ms.locfileid: "43670756"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)

Questo è l'attività finale della Guida rapida di WCF Data Services. In questa attività verranno aggiungere un'applicazione console alla soluzione, aggiungere un riferimento di [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] inseriti in questa nuova applicazione client e il feed OData dall'applicazione client usando le classi del servizio dati client generate e le librerie client di accesso .

> [!NOTE]
> Per accedere a un feed di dati non è necessario disporre di un'applicazione client basata su .NET Framework. Il servizio dati è accessibile da qualsiasi componente dell'applicazione che utilizza un feed OData. Per altre informazioni, vedere [utilizza un servizio dati in un'applicazione Client](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).

## <a name="to-create-the-client-application-by-using-visual-studio"></a>Per creare l'applicazione client tramite Visual Studio

1.  Nella **Esplora soluzioni**, fare doppio clic la soluzione, fare clic su **Add**, quindi fare clic su **nuovo progetto**.

2.  Nel riquadro sinistro, selezionare **Installed** > [**Visual c#** oppure **Visual Basic**] > **Desktop di Windows**e quindi selezionare il **App WPF** modello.

3.  Immettere `NorthwindClient` per il nome del progetto e quindi fare clic su **OK**.

4.  Aprire il file MainWindow.xaml e sostituire il codice XAML con il codice seguente:

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a>Per aggiungere un riferimento al servizio dati nel progetto

1.  Nella **Esplora soluzioni**, pulsante destro del mouse sul progetto NorthwindClient, scegliere **Add** > **riferimento al servizio**, quindi fare clic su **Discover** .

     Verrà visualizzato il servizio dati Northwind creato nella prima attività.

2.  Nel **Namespace** casella di testo, digitare `Northwind`, quindi fare clic su **OK**.

     Verrà aggiunto un nuovo file di codice al progetto, che contiene le classi di dati usate per accedere e interagire con le risorse del servizio dati come oggetti. Le classi di dati vengono create nello spazio dei nomi `NorthwindClient.Northwind`.

## <a name="to-access-data-service-data-in-the-wpf-application"></a>Per accedere ai dati del servizio dati nell'applicazione WPF

1.  Nelle **Esplora soluzioni** sotto **NorthwindClient**, fare clic sul progetto e fare clic su **Aggiungi riferimento**.

2.  Nel **Aggiungi riferimento** finestra di dialogo, fare clic sulla **.NET** scheda, selezionare l'assembly dll e quindi fare clic su **OK**.

3. Nelle **Esplora soluzioni** sotto **NorthwindClient**, aprire la tabella codici per il file MainWindow. XAML e aggiungere il codice seguente `using` istruzione (`Imports` in Visual Basic).

     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]

3.  Inserire il codice seguente che consente di eseguire una query sul servizio dati e di associare il risultato a un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> nella classe `MainWindow`:

    > [!NOTE]
    > È necessario sostituire il nome host `localhost:12345` con il server e la porta di hosting dell'istanza del servizio dati Northwind.

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]

4.  Inserire il codice seguente che consente di salvare le modifiche nella classe `MainWindow`:

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a>Per compilare ed eseguire l'applicazione NorthwindClient

1.  Nelle **Esplora soluzioni**del mouse sul progetto NorthwindClient e scegliere **imposta come progetto di avvio**.

2.  Premere **F5** per avviare l'applicazione.

     La soluzione viene compilata e l'applicazione client viene avviata. I dati vengono richiesti dal servizio e visualizzati nella console.

3.  Modificare un valore di **Quantity** colonna della griglia dei dati e quindi fare clic su **salvare**.

     Le modifiche vengono salvate nel servizio dati.

    > [!NOTE]
    > Questa versione dell'applicazione NorthwindClient non supporta l'aggiunta e l'eliminazione di entità.

## <a name="next-steps"></a>Passaggi successivi

L'applicazione client che accede al feed Northwind OData di esempio creato correttamente. È stata inoltre completata la Guida rapida di WCF Data Services.

Per altre informazioni sull'accesso a OData feed da un [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] dell'applicazione, vedere [libreria Client di WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).

## <a name="see-also"></a>Vedere anche

- [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
- [Risorse](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
