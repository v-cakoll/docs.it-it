---
title: Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 41ade767-eeab-437d-9121-9797e8fb8045
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 563d08a5907c8248a74ba992de17ac3dd0679827
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="creating-the-net-framework-client-application-wcf-data-services-quickstart"></a>Creazione dell'applicazione client .NET Framework (Guida rapida di WCF Data Services)
Questo è l'attività finale del [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] avvio rapido. In questa attività verrà aggiunta un'applicazione console alla soluzione, aggiungere un riferimento al [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed in questa nuova applicazione client e accesso di [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed dall'applicazione client utilizzando le classi del servizio dati client generate e client librerie.  
  
> [!NOTE]
>  Per accedere a un feed di dati non è necessario disporre di un'applicazione client basata su .NET Framework. L'accesso al servizio dati può essere eseguito da qualsiasi componente dell'applicazione che usa un feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]. Per ulteriori informazioni, vedere [utilizza un servizio dati in un'applicazione Client](../../../../docs/framework/data/wcf/using-a-data-service-in-a-client-application-wcf-data-services.md).  
  
### <a name="to-create-the-client-application-by-using-visual-studio"></a>Per creare l'applicazione client tramite Visual Studio  
  
1.  In **Esplora**destro la soluzione, fare clic su **Aggiungi**, quindi fare clic su **nuovo progetto**.  
  
2.  In **tipi di progetto**, fare clic su **Windows**, quindi selezionare **applicazione WPF** nel **modelli** riquadro.  
  
3.  Immettere `NorthwindClient` per il nome del progetto e quindi fare clic su **OK**.  
  
4.  Aprire il file MainWindow.xaml e sostituire il codice XAML con il codice seguente:  
  
     [!code-xaml[Astoria Quickstart Client#Window1Xaml](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml#window1xaml)]  
  
### <a name="to-add-a-data-service-reference-to-the-project"></a>Per aggiungere un riferimento al servizio dati nel progetto  
  
1.  Fare clic sul progetto NorthwindClient, fare clic su **Aggiungi riferimento al servizio**, quindi fare clic su **Discover**.  
  
     Verrà visualizzato il servizio dati Northwind creato nella prima attività.  
  
2.  Nel **Namespace** nella casella di testo `Northwind`, quindi fare clic su **OK**.  
  
     Verrà aggiunto un nuovo file di codice al progetto, che contiene le classi di dati usate per accedere e interagire con le risorse del servizio dati come oggetti. Le classi di dati vengono create nello spazio dei nomi `NorthwindClient.Northwind`.  
  
### <a name="to-access-data-service-data-in-the-wpf-application"></a>Per accedere ai dati del servizio dati nell'applicazione WPF  
  
1.  In **Esplora** in **NorthwindClient**, fare clic sul progetto e fare clic su **Aggiungi riferimento**.  
  
2.  Nella finestra di dialogo Aggiungi riferimento, fare clic su di **.NET** scheda, selezionare l'assembly System.Data.Services.Client.dll e quindi fare clic su **OK**. In **Esplora** in **NorthwindClient**, aprire la tabella codici per il file MainWindow. XAML e aggiungere le seguenti `using` istruzione (`Imports` in Visual Basic).  
  
     [!code-csharp[Astoria Quickstart Client#Using](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#using)]
     [!code-vb[Astoria Quickstart Client#Using](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#using)]  
  
3.  Inserire il codice seguente che consente di eseguire una query sul servizio dati e di associare il risultato a un oggetto <xref:System.Data.Services.Client.DataServiceCollection%601> nella classe `MainWindow`:  
  
    > [!NOTE]
    >  È necessario sostituire il nome host `localhost:12345` con il server e la porta di hosting dell'istanza del servizio dati Northwind.  
  
     [!code-csharp[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#querycode)]
     [!code-vb[Astoria Quickstart Client#QueryCode](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#querycode)]  
  
4.  Inserire il codice seguente che consente di salvare le modifiche nella classe `MainWindow`:  
  
     [!code-csharp[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria quickstart client/cs/window1.xaml.cs#savechanges)]
     [!code-vb[Astoria Quickstart Client#SaveChanges](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria quickstart client/vb/window1.xaml.vb#savechanges)]  
  
### <a name="to-build-and-run-the-northwindclient-application"></a>Per compilare ed eseguire l'applicazione NorthwindClient  
  
1.  In **Esplora**del mouse sul progetto NorthwindClient e scegliere **imposta come progetto di avvio**.  
  
2.  Premere F5 per avviare l’applicazione.  
  
     La soluzione viene compilata e l'applicazione client viene avviata. I dati vengono richiesti dal servizio e visualizzati nella console.  
  
3.  Modificare un valore di **quantità** colonna della griglia di dati e quindi fare clic su **salvare**.  
  
     Le modifiche vengono salvate nel servizio dati.  
  
    > [!NOTE]
    >  Questa versione dell'applicazione NorthwindClient non supporta l'aggiunta e l'eliminazione di entità.  
  
## <a name="next-steps"></a>Passaggi successivi  
 La creazione dell'applicazione client che accede al feed [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Northwind di esempio è stata completata. È stata inoltre completata la guida rapida di [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]l'accesso a un [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed da un [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] applicazione, vedere [libreria Client di WCF Data Services](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Introduzione](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [Risorse](../../../../docs/framework/data/wcf/wcf-data-services-resources.md)
