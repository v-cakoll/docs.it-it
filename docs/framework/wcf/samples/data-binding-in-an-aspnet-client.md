---
title: Data binding in un client ASP.NET
ms.date: 03/30/2017
ms.assetid: 68b49fa6-94e7-4d4c-a34e-902a2b3770b6
ms.openlocfilehash: 134e1d7df3ed6bb245a870ad257fa64ad94e4e9c
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602596"
---
# <a name="data-binding-in-an-aspnet-client"></a>Data binding in un client ASP.NET
In questo esempio viene illustrato come associare i dati restituiti da un tipico servizio Windows Communication Foundation (WCF) in un'applicazione Web Form.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo argomento.  
  
 In questo esempio viene illustrato un servizio che implementa un contratto in cui viene definito un modello di comunicazione request/reply. L'esempio è costituito da un'applicazione Web form client accessibile da un browser e un servizio WCF ospitato da Internet Information Services (IIS).  
  
 Il servizio implementa un contratto che definisce un modello di comunicazione richiesta/risposta. Il contratto viene definito mediante l'interfaccia `IWeatherService`, che espone un'operazione denominata `GetWeatherData`. Questa operazione accetta una matrice di città e restituisce una matrice di oggetti `WeatherData` che rappresentano la temperatura massima e minima prevista per una città.  
  
 Nella pagina client. aspx di ASP.NET viene definito un controllo Web DataGrid, che contiene la rappresentazione grafica dei dati restituiti dal servizio. Il codice nella pagina aspx chiama il servizio WCF per i dati meteo e restituisce i dati a una matrice di `WeatherData` oggetti. Il DataGrid specifica dove ottenere i dati impostando la proprietà `DataSource` su quella matrice. Si verifica il data binding con una chiamata al metodo `DataBind` del DataGrid. Tutto questo codice è contenuto all'interno di.`aspx` `Page_Load`il metodo della pagina, quindi, ogni volta che l'utente aggiorna la pagina del browser, i dati vengono aggiornati in DataGrid.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Il client di questo esempio è un sito Web che è in esecuzione sotto un server Web di sviluppo. Per avviare il server Web di sviluppo, digitare quanto segue al prompt dei comandi: `%SystemDrive%\Program Files\Common Files\Microsoft Shared\DevServer\9.0\WebDev.WebServer.EXE" /port:8000 /path:<WebFormsSamplePath>\CS\client /vpath:/client` . Quindi passare a `http://localhost:8000/client` . Per eseguire questo esempio tra più computer, sostituire tutti i riferimenti a `localhost` nel file Web.config del client con il nome del computer che ospita il server.  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) ed esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti i Windows Communication Foundation (WCF) ed [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WebForms`
