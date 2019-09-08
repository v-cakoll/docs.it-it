---
title: Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
ms.openlocfilehash: 9995a509bf997298d991a1f66cfdf3cae6cd0395
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2019
ms.locfileid: "70790957"
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)

Questa è l'attività finale della Guida introduttiva WCF Data Services. In questa attività si aggiungerà un'applicazione console alla soluzione, si aggiungerà un riferimento al [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed in questa nuova applicazione client e si accederà al feed OData dall'applicazione client utilizzando le classi del servizio dati client e le librerie client generate. .

> [!NOTE]
> Per accedere a un feed di dati non è necessario disporre di un'applicazione client basata su .NET Framework. Il servizio dati può accedere a qualsiasi componente dell'applicazione che utilizza un feed OData. Per ulteriori informazioni, vedere [utilizzo di un servizio dati in un'applicazione client](using-a-data-service-in-a-client-application-wcf-data-services.md).

## <a name="to-create-the-client-application-by-using-visual-studio"></a>Per creare l'applicazione client tramite Visual Studio

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sulla soluzione, scegliere **Aggiungi**, quindi fare clic su **nuovo progetto**.

2. Nel riquadro sinistro selezionare **installato** > [ **C# Visual** o **Visual Basic**] > Desktop di **Windows**, quindi selezionare il modello **applicazione WPF** .

3. Immettere `NorthwindClient` per il nome del progetto, quindi fare clic su **OK**.

4. Aprire il file MainWindow.xaml e sostituire il codice XAML con il codice seguente:

     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml#window1xaml)]

## <a name="to-add-a-data-service-reference-to-the-project"></a>Per aggiungere un riferimento al servizio dati nel progetto

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto NorthwindClient, scegliere **Aggiungi** > **riferimento al servizio**, quindi fare clic su **individua**.

     Verrà visualizzato il servizio dati Northwind creato nella prima attività.

2. Nella casella di testo **spazio dei nomi** Digitare `Northwind`, quindi fare clic su **OK**.

     Verrà aggiunto un nuovo file di codice al progetto, che contiene le classi di dati usate per accedere e interagire con le risorse del servizio dati come oggetti. Le classi di dati vengono create nello spazio dei nomi `NorthwindClient.Northwind`.

## <a name="to-access-data-service-data-in-the-wpf-application"></a>Per accedere ai dati del servizio dati nell'applicazione WPF

1. In **Esplora soluzioni** in **NorthwindClient**fare clic con il pulsante destro del mouse sul progetto e scegliere **Aggiungi riferimento**.

2. Nella finestra di dialogo **Aggiungi riferimento** fare clic sulla scheda **.NET** , selezionare l'assembly System. Data. Services. client. dll, quindi fare clic su **OK**.

3. In **Esplora soluzioni** in **NorthwindClient**aprire la tabella codici per il file MainWindow. XAML e aggiungere l'istruzione seguente `using` (`Imports` in Visual Basic).

    [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#using)]
    [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#using)]

4. Inserire il codice seguente che consente di eseguire una query sul servizio dati e di associare il risultato a un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> nella classe `MainWindow`:

    > [!NOTE]
    > È necessario sostituire il nome host `localhost:12345` con il server e la porta di hosting dell'istanza del servizio dati Northwind.

     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#querycode)]

5. Inserire il codice seguente che consente di salvare le modifiche nella classe `MainWindow`:

     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_quickstart_client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_quickstart_client/vb/window1.xaml.vb#savechanges)]

## <a name="to-build-and-run-the-northwindclient-application"></a>Per compilare ed eseguire l'applicazione NorthwindClient

1. In **Esplora soluzioni**fare clic con il pulsante destro del mouse sul progetto NorthwindClient e selezionare **Imposta come progetto di avvio**.

2. Premere **F5** per avviare l'applicazione.

     La soluzione viene compilata e l'applicazione client viene avviata. I dati vengono richiesti dal servizio e visualizzati nella console.

3. Modificare un valore nella colonna **Quantity** della griglia dei dati, quindi fare clic su **Save**.

     Le modifiche vengono salvate nel servizio dati.

    > [!NOTE]
    > Questa versione dell'applicazione NorthwindClient non supporta l'aggiunta e l'eliminazione di entità.

## <a name="next-steps"></a>Fasi successive

È stata creata correttamente l'applicazione client che accede al feed OData di esempio Northwind. È stata anche completata la Guida introduttiva WCF Data Services.

Per ulteriori informazioni sull'accesso a un feed OData da un'applicazione .NET Framework, vedere la pagina relativa alla [libreria Client WCF Data Services](wcf-data-services-client-library.md).

## <a name="see-also"></a>Vedere anche

- [Introduzione](getting-started-with-wcf-data-services.md)
- [Risorse](wcf-data-services-resources.md)
