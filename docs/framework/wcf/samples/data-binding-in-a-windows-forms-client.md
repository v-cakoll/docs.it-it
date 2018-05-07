---
title: data binding in un client Windows Form
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: a84aeedba89cc7a5c267a0fd1f6c4f604fe80d43
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="data-binding-in-a-windows-forms-client"></a>data binding in un client Windows Form
Questo esempio viene illustrato come associare ai dati restituiti da un servizio Windows Communication Foundation (WCF) in un'applicazione Windows Form.  
  
> [!NOTE]
>  La procedura di installazione e le istruzioni di compilazione per questo esempio si trovano alla fine di questo articolo.  
  
 In questo esempio viene illustrato un servizio che implementa un contratto in cui viene definito un modello di comunicazione request/reply. L'esempio è costituito da un'applicazione Windows Form client (.exe) e da un servizio di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] ospitato su Internet Information Services (IIS).  
  
 Il contratto viene definito mediante l'interfaccia `IWeatherService`, che espone un'operazione denominata `GetWeatherData`. Questa operazione accetta una matrice di città e restituisce una matrice di oggetti `WeatherData` che rappresentano la temperatura massima e minima prevista per una città.  
  
 L'associazione di dati si verifica sul client dell'applicazione Windows Form. Nella finestra di progettazione Windows Form viene definito un elemento `DataGridView`, che costituisce una rappresentazione grafica dei dati. Viene creato anche un intermediario denominato `BindingSource`. L'origine dati di `BindingSource` è impostata sulla matrice dei dati restituita dal servizio. Lo scopo dell'elemento `BindingSource` consiste nel fornire un livello di riferimento indiretto tra i dati e la visualizzazione dei dati. Tutte le interazioni con i dati, ad esempio l'esplorazione, l'ordinamento, il filtro e l'aggiornamento, vengono eseguite mediante chiamate al componente `BindingSource`. Per eseguire l'associazione di dati all'oggetto `DataGridView`, l'elemento `datasource` di  `DataGridView` viene impostato sull'oggetto `BindingSource`. Tutti i dati restituiti dal servizio di [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] vengono visualizzati graficamente dall'utente.  Ogni volta che l'utente fa clic sul pulsante, i dati restituiti vengono automaticamente aggiornati nell'oggetto `DataGridView` associato a dati.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Per impostare, compilare ed eseguire l'esempio  
  
1.  Assicurarsi di avere eseguito la [procedura di installazione singola per gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Per compilare l'edizione in C# o Visual Basic .NET della soluzione, seguire le istruzioni in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Per eseguire l'esempio in una configurazione singola o tra computer, seguire le istruzioni in [esegue gli esempi di Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  È possibile che gli esempi siano già installati nel computer. Verificare la directory seguente (impostazione predefinita) prima di continuare.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Se questa directory non esiste, andare al [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) per scaricare tutti i Windows Communication Foundation (WCF) e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] esempi. Questo esempio si trova nella directory seguente.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a>Vedere anche
