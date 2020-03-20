---
title: Associazione dati in un client Windows Form
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: d538e8a525f8d07e9ac9f57d4b10119907602d90
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145046"
---
# <a name="data-binding-in-a-windows-forms-client"></a>Associazione dati in un client Windows Form
In questo esempio viene illustrato come eseguire l'associazione ai dati restituiti da un servizio Windows Communication Foundation (WCF) in un'applicazione Windows Form.This sample demonstrates how to bind to data returned by a Windows Communication Foundation (WCF) service in a Windows Forms application.  
  
> [!NOTE]
> La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo articolo.  
  
 In questo esempio viene illustrato un servizio che implementa un contratto in cui viene definito un modello di comunicazione request/reply. L'esempio è costituito da un'applicazione Windows Form client (.exe) e un servizio WCF ospitato da Internet Information Services (IIS).  
  
 Il contratto viene definito mediante l'interfaccia `IWeatherService`, che espone un'operazione denominata `GetWeatherData`. Questa operazione accetta una matrice di città e restituisce una matrice di oggetti `WeatherData` che rappresentano la temperatura massima e minima prevista per una città.  
  
 Il data binding si verifica sul client dell'applicazione Windows Form. Nella finestra di progettazione Windows Form viene definito un elemento `DataGridView`, che costituisce una rappresentazione grafica dei dati. Viene creato anche un intermediario denominato `BindingSource`. L'origine dati di `BindingSource` è impostata sulla matrice dei dati restituita dal servizio. Lo scopo dell'elemento `BindingSource` consiste nel fornire un livello di riferimento indiretto tra i dati e la visualizzazione dei dati. Tutte le interazioni con i dati, ad esempio l'esplorazione, l'ordinamento, il filtro e l'aggiornamento, vengono eseguite mediante chiamate al componente `BindingSource`. Per eseguire il data binding all'oggetto `DataGridView`, l'elemento `datasource` di `DataGridView` viene impostato sull'oggetto `BindingSource`. Tutti i dati restituiti dal servizio WCF vengono quindi visualizzati graficamente all'utente.  Ogni volta che l'utente fa clic sul pulsante, i dati restituiti vengono automaticamente aggiornati nell'oggetto `DataGridView` associato a dati.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1. Assicurarsi di aver eseguito la procedura di [installazione una tantera per Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Per eseguire l'esempio in una configurazione su un singolo o più computer, seguire le istruzioni in Esecuzione di [Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Se questa directory non esiste, passare a [Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) Esempi per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) per scaricare tutti gli esempi e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Windows Communication Foundation (WCF). Questo esempio si trova nella directory seguente.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
